---
title: Use tags to organize files on Windows
---

Tags are a way to organize your files and folders. You can assign one or more tags to any file or folder, and then use the tags to filter and sort your files. You can also use tags to search for your files.
	
## How to assign tags

To assign a tag to a file or folder, follow these steps:

- Right-click the file or folder you want to tag.
- Click on the “Edit file tags” menu that appears.
- Select a tag from the list.

You can also assign tags by dragging and dropping files or folders onto existing tags in the sidebar.

## How to view and filter by tags

To view and filter your files by tags, follow these steps:

- You will see a list of your tags at the bottom of the left-hand sidebar.
- Tap on a tag to see all the files or folders with that tag.

You can also click tags in the Details layout to start a search. To do that, follow these steps:

- Switch to the Details layout, there will be a tag column where you can see tags assigned to your files and folders.
- Click the tag you want to search for.
- You will see a list of all the files or folders with that tag.

## How to search for tags

To search for tags, follow these steps:

- Tap on the search box and type in `tag:` followed by the name of the tag, for example `tag: Photos`.
- You can search for multiple tags at once by separating tag names with a comma and space. For example `tag: Photos, Important`.

## How to edit or delete tags

You can create and edit tags from the Advanced section in Settings. To do that, follow these steps:

- Click the “Settings” icon in the top right corner of the screen.
- Click “Advanced” in the menu that appears.
- Click “Tags”.
- You will see a list of all tags.
- You can click the “New tag” button to create a new tag, or use the “Edit” and “delete” buttons on existing tags to edit or delete them.
- If you choose to edit, you can change the name and or color of the tag.

Note that deleting a tag will not delete the files or folders with that tag, but it will remove the tag from those items.


## Tags widget

The Tags widget on the home page helps you organize and access your tagged files and folders. This widget shows you all the tags you have created and the files and folders that have those tags. To enable or disable the Tags widget, go to the Preferences section in Settings, and toggle the switch under the Widgets section.

## How do tags work behind the scenes?

Instead of creating a database with a list of files and tags, we store the tag information in the file itself using alternate data streams. This allows:
- Users to move files around without losing their tags.
- It decouples the tags feature from Files and allows other apps using the same system to support this feature.
