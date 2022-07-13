# Getting Started

Getting started with local development happens in two parts, cloning this repository and setting up your Retool application to listen to it.

## Setting up local environment

```shell
yarn install
yarn dev
```

After starting the webpack dev server with `yarn dev` and the example dev server servers your built javascript at `http://localhost:8080/main.js`. Once the dev server is running, open up a Retool application, drag a custom component in and place the following in the iframe code:

```html
<script type="text/javascript" src="http://localhost:8080/index.js" />
```

### Example Retool Model

```
{
  data: {{ formatDataAsArray(query6.data) }},
  updated_data: [],
  fields: ['project','lob','work_type','amount', 'pr_code'],
  labels: ['Project', 'LOB', 'Work Type','Amount', 'PR Code'],
  groups: [
    'project', 'lob'
  ],
  pivot: 'work_type',
  value: 'amount',
  id: 'pr_code',
  totals: {
    row_total: false,
    sub_total: false,
    grand_total: false,
  },
  columnSorting: true,
  fixedColumnsStart: 1
}
```

Required Model Keys
- data
- fields
- labels
- groups
- pivot
- value
- id