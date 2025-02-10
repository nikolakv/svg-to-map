# Custom SVG Overlay on Leaflet Map

This project demonstrates how to overlay an SVG on a Leaflet map, allowing you to interactively transform it (via dragging) and generate geographic points along a selected SVG `<path>`. The application converts user-input distances (in meters) into SVG-native pixels using the current map scale, generates points along the SVG path, and exports the resulting points as a GeoJSON file.

## Features

- **SVG Upload & Parsing:**  
  Upload your own SVG and have its intrinsic dimensions used to create a geographic overlay.

- **Interactive Transformation:**  
  Use drag operations (powered by [svg.js](https://svgjs.dev/) and its `svg.draggable` plugin) to translate the SVG on the map.

- **Point Generation Along an SVG Path:**  
  Generate points along a selected `<path>` using the [svg-path-properties](https://github.com/rveciana/svg-path-properties) library.

- **Distance Conversion:**  
  Input minimum and maximum distances in meters. The app converts these into SVG pixels based on the current map scale, ensuring the spacing is geographically accurate.

- **GeoJSON Export:**  
  Export the generated points as a GeoJSON file for further use in other applications.

## Prerequisites

- A modern web browser (Chrome, Firefox, Edge, etc.)
- A local web server (optional but recommended) for serving the files. You can use:
  - The VSCode [Live Server extension](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)
  - Python's built-in web server (run `python -m http.server` in the project directory)

## Project Structure
├── index.html # Main HTML file (custom SVG overlay implementation)
├── js
│ └── libs
│ └── svg-path-properties.js # UMD build of svg-path-properties
└── README.md



## How to Run

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/your-username/your-repo.git
   cd your-repo
   ```

2. **Open the Project:**
   - Either open `index.html` directly in your browser or serve the project using a local web server.

3. **Use the Application:**
   - **Upload your SVG:** Click the file input and select an SVG file.
   - **Select an SVG Path:** Once the SVG is loaded, choose a `<path>` from the dropdown.
   - **Configure Distance:** Enter minimum and maximum distances in **meters**.
   - **Generate Points:** Click the "Generate Points" button to generate and display points along the selected path.
   - **Export GeoJSON:** Click the "Export GeoJSON" button to download the generated points as a GeoJSON file.

## Customization & Extensions

- **Scaling and Rotation:**  
  Currently, the project supports translation (dragging) only. If you wish to add more complex transformations like scaling or rotation, you may need to adjust the conversion logic and update the overlay's bounds accordingly.

- **UI Labels:**  
  The input fields for distance now reflect meters instead of pixels. If needed, further UI or documentation changes can be made to clarify that all distance inputs are in meters.

## Dependencies

- [Leaflet](https://leafletjs.com/) (for map rendering)
- [svg.js](https://svgjs.dev/) (for SVG manipulation)
- [svg.draggable.js](https://github.com/svgdotjs/svg.draggable.js) (for drag support with svg.js)
- [svg-path-properties](https://github.com/rveciana/svg-path-properties) (for generating points along SVG paths)

All dependencies are loaded either via CDNs or from local files (make sure the file path for `svg-path-properties.js` is correct).

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Thanks to the developers of [Leaflet](https://leafletjs.com/), [svg.js](https://svgjs.dev/), and [svg-path-properties](https://github.com/rveciana/svg-path-properties) for the great libraries.
- Inspired by practical use cases for georeferencing SVG content on maps.
