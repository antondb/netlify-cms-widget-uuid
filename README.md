# netlify-cms-widget-uuid
Netlify CMS plugin to support UUID widgets.

Widgets are inputs for the Netlify CMS editor interface. It's a React component that receives user input and outputs a serialized value.

NetlifyCMS offers the ability to add referential links between collections. It unfortunately does not provide a key widget to safely link between items.

## Install

As an npm package:

1) Install the widget:
```
npm i netlify-cms-widget-uuid-v4
```

2) Import the UUID widget in the netlifyCMS file:
```
import {UuidControl, UuidPreview} from 'netlify-cms-widget-uuid-v4';
```

3) Register the widget ready for use:
```
CMS.registerWidget('uuid', UuidControl, UuidPreview)

```

Via `script` tag:
```html
<script src="https://unpkg.com/netlify-cms-widget-uuid-v4@^1.0.12/dist/index.js"></script>
<script type="text/javascript">
  CMS.registerWidget('uuid', uuidWidget.UuidControl, uuidWidget.UuidPreview)
</script>
```

## How to use

Inside the YML collections file use the new widget.

```
collections:
  - name: "example"
    label: "Example"
    folder: "/path/to/your/folder"
    create: true
    slug: "{{slug}}"
    fields:
      - {label: "ID", name: "id", widget: "uuid"}
```
