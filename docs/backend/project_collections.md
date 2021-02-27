---
id: project_collections
title: Project Collections
sidebar_label: Project Collections
---

import Spec from "@theme/Spec";
const defaultImageFormats = "GIF, JPEG, JPG, PNG";

## About

Project Collections group and associate Projects with one another on your instance’s homepage, overriding the default “Our Projects” library view from that space. Collections also appear in two other places on the frontend:

```bash title="1. A page gathering all Project Collections"
https://{domain-name}/projects/project-collections
```

``` bash title="2. A page specific to each individual Project Collection"
https://{domain-name}/projects/project-collection/{collection-slug}
```

## Interface

<Spec
    title="Accessing this view"
    items={[
        { key: "Backend Location", value: "Projects → Project Collections" },
        { key: "Required User Role", value: "Admin, Editor, or Marketeer" },
    ]}
/>

### Sidebar

The sidebar displays a list of all existing Project Collections on your instance and a button to create new ones.

Each entry on the sidebar list includes the title of the collection, the number of projects contained within the collection, a visibility button, and drag bars.

The title, visibility button, and drag bars are all selectable by mouse or keyboard from this list with a click or by pressing the space bar, respectively.

- **Title**. Selecting the title of a collection will open its contents and settings in the editing pane in the main body of this page.
- **Visibility**. Activating the eye icon will hide the collection from *all* frontend views. When hidden, the eye icon will be shown with a diagonal slash across it. This button *does not* affect whether or not a Collection appears on the homepage—that is configured separately in the Collection’s settings.  
- **Drag Bars**. Appearing as two parallel, horizontal lines, you can use these to adjust the display order of the Collections (for both the home and Collections pages), either by clicking and dragging an entry with your mouse or by pressing the space bar and then either the up or down arrow keys on your keyboard.

Beneath the list of Collections is the `+ Create New Collection` button that opens a drawer from the right of the screen will a number of fields you can use to define the parameters of your new Project Collection.

### Editing Pane

The editing pane displays a header with the Collection’s title and buttons to adjust its settings. For Manual Collections, the header also includes a button to manage which projects are part of the Collection.

- **Settings**. When you click `Settings`, a drawer will open from the right of the screen with a number of fields that allow you to configure the Collection. These function of these fields are described in the following sections.
- **Manage Projects**. This button only appears in the header of Manual Collections. Selecting this button opens a drawer from the right where you can search or page through all the projects contained in the instance and manually add them to the collection with your mouse or keyboard.

Below the header, the `Order Collection By` dropdown determines how the projects in the Collection are ordered (e.g., by creation date, title). Manual Collections include a switch that makes its possible for you to bypass the pre-defined sorting categories and order the collection manually with your mouse or keyboard.

A view of all the Projects in the Collection follows below the ordering options. Manual Collections will show as a vertical list that you can scroll from top to bottom in a single view. Smart collections will show Projects in a paginated grid. Selecting a project from this view takes you to that Project detail page.

## General Collection Settings

The settings in this section are common to both Manual and Smart Collections.

### Collection Title

This title appears in library views at the top of the Collection beside the (optional) Collection Icon. This field is presently limited to plain text and does not accept Markdown or HTML syntax. A title is required to save a new Collection.

### Manual or Smart Collection

Manual Collections allow you to directly pick and choose projects to add to a Collection using your mouse or keyboard. Smart Collections rely on you to set parameters the system will use to automatically populate and update the Collection.

Most Collection settings are shared by both Manual 

Manifold updates the list of Projects in Smart Collections every fifteen minutes. Adjusting and saving new settings to a Smart Collection will immediately refresh the cache of Projects in that collection.

### Slug

The slug appears as the last component of the URL for the Collection’s homepage:

``` bash
https://{domain-name}/projects/project-collection/{collection-slug}
```

If left blank, Manifold will adapt the Collection’s title to suit as the slug.

### Description

The description is rendered below the Collection title in library views and can be styled with Markdown syntax. 

### Hero Image and Layout

The Collection Hero is an image that provides a visual identity to Collections in library views. Image files can be dropped onto the `Hero Image` field or selected using your device’s file system by clicking the `Upload a File` link.

The Hero will render according to your selection under `Hero Layout` as follows:

- **Square Inset**. Rendered as a square, the Hero will appear to the left of both the Collection Title and Description.
- **Wide Inset**. Matching the width of the library container, the Hero will appear between the Collection Title and Description.
- **Full Bleed**. The width of the hero will adapt to match the size of browser or viewport.

<Spec
    title="Collection Hero Specs"
    items={[
        { key: "Square Inset Width", value: "340 px" },
        { key: "Wide Inset Width", value: "1135 px" },
        { key: "Full Bleed Width", value: "Responsive" },
        { key: "Height (for all layouts)", value: "340 px" },
        { key: "Format", value: defaultImageFormats },
    ]}
/>

### Visible

This toggle controls whether or not the Collection appears on the Manifold frontend. In the off position, the Collection will not appear on either the home or Collection pages. When toggled on, the Collection will appear ***only*** on the Project Collections page.

### Show on Homepage

This toggle promotes Collections that are visible (see above) to the instance’s homepage. It is not possible to have a Collection appear only on the homepage and not on the Collection page.

There is no artificial limit to the number of Collections that can appear on the homepage, but the more Collections that appear, the slower the page will be to load.

### Collection Icon

Manifold includes seven system icons you can choose from to associate with the Collection’s title in library views: a stack of books laying flat, a lamp, a “New” badge, three books standing with spines out, a globe, a pointing finger, and a mug.

The Collection Icon is optional and can be selected (or deselected) using your mouse or keyboard.

The Collection Icon is overridden by the Custom Icon when present.

### Custom Icon

Functionally the same as the Collection Icon, a Custom Icon gives you the option to upload your own icon image file instead of using a system one.

Icon files can be dropped onto the `Custom Icon` field or selected using your device’s file system by clicking the `Upload a File` link.

<Spec
    title="Custom Icon Specs"
    items={[
        { key: "Width", value: "60 px" },
        { key: "Height", value: "60 px" },
        { key: "Format", value: defaultImageFormats },
    ]}
/>

### Social Card Image, Title, and Description

When sharing the URL for a Collection’s homepage, Manifold includes Open Graph metadata that social media platforms display in posts as ”cards”. Cards are made up of the following elements.

- **Image**. Images should be prepared in an 8:5 ratio. When this field is left blank, Manifold will supply the Collection Hero image in its place, or, if there is no Collection Hero, the instance’s [Header Logo](../administering/configuring/theme_settings.md). Image files can be dropped onto the `Social Card Image` field or selected using your device’s file system by clicking the `Upload a File` link.

	<Spec
	    title="Social Card Image Specs"
	    items={[
	        { key: "Width", value: "640 px" },
	        { key: "Height", value: "400 px" },
	        { key: "Format", value: defaultImageFormats },
	    ]}
	/>

- **Title**. The `Collection Title` text is the default value.
- **Description**. Manifold will supply text from the collection’s `Description` when this field is left blank. If the Collection has no description, the system will use the [`Default Page Description`](../administering/configuring/general_settings.md).

	Markdown formatting ***is not*** honored in Open Graph metadata. Coding syntax will render as plain text in social media cards.

## Settings Specific to Smart Collections

The following settings are only available to Smart Collections. Each serves as a filter the system uses to create and maintain the roster of Projects in the Collection. Only those Projects that match ***all*** the set criteria are included in the Collection.

### Number of Projects

By default, Manifold caps the number of Projects the system will ***display*** in a Collection to eight. Projects that meet the Collection’s inclusion criteria beyond that limit are still indexed as part of the Collection; however only those eight that match the `Order Collection By` sorting filter (see [Editing Pane](../backend/project_collections.md#editing-pane) above) will render in library views.

You can adjust the default limit higher or lower here—we recommend by fours, since the library view spans four Projects—***or*** you can remove the limit entirely by clearing the number from this field and saving it blank.

### Featured Projects

This toggle limits the Collection to accepting just those Projects that have been marked as [`Featured`](../backend/projects.md#featured).

### Show Projects with These Subjects or Tags

These two dropdowns surface existing Subjects and Tags to limit which projects are accepted into the Collection. You can nominate multiple Subjects or Tags as filters.

Existing filters appear below the respective dropdown and can be removed as Collection criteria from that space with your mouse or keyboard.



