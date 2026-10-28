# Onshape Makerspace Tutorial: Parametric Workbench

Welcome to the Makerspace! In this tutorial, we will design a sturdy, fully parametric workbench. By using variables, you can easily adjust the size of this workbench later to fit any corner of your workshop.

Below is the final workbench we will be designing:

Follow the steps below. Watch the short video snippets for a visual guide on each feature.

## Step 1: Define Overall Workbench Dimensions

<iframe width="560" height="315" src="https://www.youtube.com/embed/YOUR_VIDEO_ID_HERE" title="Step 1 Video" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Before drawing anything, we want to establish the maximum envelope of our workbench using variables. This makes it easy to resize the table later without breaking the model.

1. Open the **Variable** tool in the top toolbar.
2. Create the following three variables:
   * `#workbench_width = 1500 mm`
   * `#workbench_depth = 800 mm`
   * `#workbench_height = 1000 mm`

## Step 2: Define Framing Lumber Sizes

<iframe width="560" height="315" src="https://www.youtube.com/embed/YOUR_VIDEO_ID_HERE" title="Step 2 Video" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Next, we need to define the thickness of the wood or metal we are using for the frame. By making these variables, you can easily switch between 2x4s, 4x4s, or custom steel tubing.

1. Create a layout sketch (`Sketch 1`) on the Top plane to define the overall footprint using your width and depth variables. Extrude (`Extrude 1`) it as a construction surface or simply keep the sketch as a reference.
2. Create two more variables:
   * `#board_width = 95 mm`
   * `#board_height = 65 mm`

## Step 3: Create and Mirror the Legs

<iframe width="560" height="315" src="https://www.youtube.com/embed/YOUR_VIDEO_ID_HERE" title="Step 3 Video" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Now we will create the first leg and mirror it to the other three corners.

1. Create `Sketch 2` on the Top plane (or the corners of your layout sketch). Draw a rectangle using `#board_width` and `#board_height`.
2. Use `Extrude 2` to pull the leg up to `#workbench_height`.
3. Use the **Mirror** tool (`Mirror 1`) to mirror the leg across the Right plane.
4. Use the **Mirror** tool again (`Mirror 2`) to mirror both legs across the Front plane, giving you 4 identical legs.

## Step 4: Build the Top Frame (Aprons)

<iframe width="560" height="315" src="https://www.youtube.com/embed/YOUR_VIDEO_ID_HERE" title="Step 4 Video" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

We need horizontal supports connecting the legs. We'll do the short sides first, then the long sides.

1. Create `Sketch 3` on the side face of a leg. Draw the short apron profile and `Extrude 3` it across to the opposite leg.
2. `Mirror 3` this short apron to the other side of the table.
3. Repeat this process: Create `Sketch 4` for the long apron, `Extrude 4` it between the legs, and use `Mirror 4` to duplicate it to the back.

## Step 5: Add Frame Cross Members

<iframe width="560" height="315" src="https://www.youtube.com/embed/YOUR_VIDEO_ID_HERE" title="Step 5 Video" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

To make the top extra sturdy, we'll add cross members. We will pattern these so that if the table gets longer, the number of supports can change.

1. Create `Sketch 5` on the top face of the frame. Draw the profile for a cross member. *(Note: If your sketch turns red, ensure it is constrained to the frame, not a mirrored plane that might have shifted).*
2. `Extrude 5` the cross member to the opposite apron.
3. Create a new variable: `#num_of_crossmembers = 6`.
4. Use the **Linear Pattern** tool (`Linear pattern 1`) to pattern the cross member along the length of the table, using your variable for the instance count.

## Step 6: Create the Bottom Shelf Frame

<iframe width="560" height="315" src="https://www.youtube.com/embed/YOUR_VIDEO_ID_HERE" title="Step 6 Video" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Instead of redrawing the frame for the bottom shelf, we can pattern the top frame downwards!

1. Create a variable for how high off the floor you want the shelf: `#ground_clearance = 400 mm`.
2. Use the **Linear Pattern** tool (`Linear pattern 2`). Select the top aprons and cross members.
3. Set the direction to point downwards along the legs, and set the distance using an equation (e.g., `#workbench_height - #ground_clearance`). Make sure the instance count is `2`.

## Step 7: Add the Work Surfaces (Top and Bottom Sheets)

<iframe width="560" height="315" src="https://www.youtube.com/embed/YOUR_VIDEO_ID_HERE" title="Step 7 Video" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Finally, we need to add the MDF or plywood sheets to act as our work surfaces.

1. Create `Sketch 6` on the very top of the table frame. Draw a rectangle that covers the frame.
2. Create a variable for your material thickness: `#sheet_thickness = 60 mm`.
3. `Extrude 6` the top surface using the `#sheet_thickness` variable.
4. Repeat this for the bottom shelf: Create `Sketch 7` on the bottom frame and `Extrude 7` it to create the lower shelf surface.

*Troubleshooting Tip: You may notice Sketches 5 and 7 showing up red in your feature tree (as seen in `image_2edd9c.png`). This usually means a reference was lost. Always try to dimension your sketches to the Origin or primary planes when possible to prevent broken references!*

**Congratulations!** You've just built a fully parametric workbench. Go back to your variable table and try changing the `#workbench_width` to 2000 mm. Watch how the entire model updates automatically!
