"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
                    Tutorial - Recommended histopathology WSI PROCESSING
            Overlaying Tissue Compartment Annotations on a Slide Image of Patient 15
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""

import os
import json
import openslide
from PIL import Image, ImageDraw

FILE_PATH = 'XXX/15.mrxs' # Replace XXX with the path to reach the mrxs file
FILE_ANNOTATION = 'YYY/15.geojson' # Replace YYY with the path to reach the GeoJSON file
LEVEL = 7 # Selected the level from the slide
CASES = ['in situ carcinoma', 'infiltrant carcinoma', 'normal tissue'] # Cases types

selected_image = openslide.OpenSlide(FILE_PATH) # Load the slide using OpenSlide

LEVEL_DOWNSAMPLE = int(selected_image.level_downsamples[LEVEL]) # Downsample factor of the selected level

# The X coordinate of the rectangle bounding the non-empty region of the slide
shift_x = selected_image.properties['openslide.bounds-x'] 
shift_x = int(shift_x)
# The Y coordinate of the rectangle bounding the non-empty region of the slide
shift_y = selected_image.properties['openslide.bounds-y']
shift_y = int(shift_y)

# Load the GeoJSON file
geojson_data = ""
with open(FILE_ANNOTATION, "r") as file:
    geojson_data = json.load(file)

# Extract the annotations
mfeatures = geojson_data['features']

# Prepare the annotations in a list where we select for each of them the coordinates and the case type
list_annotations = []
for mannotation in mfeatures:
    list_annotations.append([mannotation['geometry']['coordinates'][0], mannotation['properties']['classification']['name']])


# The height of the rectangle bounding the non-empty region of the slide at level LEVEL 
bh_LEVEL_DOWNSAMPLE = int(selected_image.properties['openslide.bounds-height'])//LEVEL_DOWNSAMPLE
# The width of the rectangle bounding the non-empty region of the slide at level LEVEL
bw_LEVEL_DOWNSAMPLE = int(selected_image.properties['openslide.bounds-width'])//LEVEL_DOWNSAMPLE

# Compute the annotations at level LEVEL
list_annotations_downsample = []
for mannotation in list_annotations:
    mannnotation_coordinates = [[x/LEVEL_DOWNSAMPLE, y/LEVEL_DOWNSAMPLE] for [x, y] in mannotation[0]]
    list_annotations_downsample.append([mannnotation_coordinates, mannotation[1]])

# Extract the rectangle bounding the non-empty region of the slide at level LEVEL
bounding_box = selected_image.read_region(location=(shift_x, shift_y), level=LEVEL, size=(bw_LEVEL_DOWNSAMPLE, bh_LEVEL_DOWNSAMPLE))
bounding_box = bounding_box.convert("RGBA")

# Create a transparent overlay image
overlay = Image.new("RGBA", bounding_box.size, (0, 0, 0, 0))
draw = ImageDraw.Draw(overlay)

# Define annotation colors based on CASES
annotation_colors = {
    CASES[0]: (255, 0, 0, 100),    # Red with transparency
    CASES[1]: (0, 0, 255, 100),    # Blue with transparency
    CASES[2]: (0, 255, 0, 100)     # Green with transparency
}

# Draw semi-transparent contours on the overlay
for annotation in list_annotations:
    coordinates = [(x / LEVEL_DOWNSAMPLE, y / LEVEL_DOWNSAMPLE) for x, y in annotation[0]]
    annotation_type = annotation[1]  # This will match CASES[0], CASES[1], or CASES[2]
    
    # Get the corresponding color
    color = annotation_colors.get(annotation_type, (255, 255, 255, 100))  # Default: white with transparency

    # Draw the contour as a semi-transparent polygon
    draw.polygon(coordinates, outline=color, fill=color)

# Blend the overlay with the slide at level LEVEL
final_image = Image.alpha_composite(bounding_box, overlay)

# Save the result
final_image.save("overlay_tissues_15.png")


