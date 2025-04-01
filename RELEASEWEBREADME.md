# FW Version Timeline Dashboard

This project displays a timeline of firmware version releases for various products. The dashboard is hosted on GitHub Pages at https://liusqu.github.io/FW-version-timeline/

## Project Structure

- `index.html`: The main and only file containing all HTML, CSS, and JavaScript code
- Branch `gh-pages`: The branch used for GitHub Pages deployment

## Data Structure

The timeline data is stored directly in the `index.html` file in the `products` array. Each product has the following structure:

```javascript
{
    "id": "d7x-w",
    "name": "D7X-W",
    "version": "3.9.2",
    "riskLevel": "released",
    "keyFeatures": ["video boundary for main camera"],
    "delayFactors": [],
    "stages": [
        {
            "name": "requirements",
            "startDate": "2025-01-10",
            "endDate": "2025-01-10"
        },
        {
            "name": "development",
            "startDate": "2025-01-10",
            "endDate": "2025-03-11"
        },
        {
            "name": "dten-qa",
            "startDate": "2025-03-11",
            "endDate": "2025-03-26"
        },
        {
            "name": "release",
            "startDate": "2025-03-26",
            "endDate": "2025-03-26"
        }
    ]
}
```

## How to Update

1. Clone the repository:
   ```bash
   git clone https://github.com/liusqu/FW-version-timeline.git
   cd FW-version-timeline
   git checkout gh-pages
   ```

2. Edit the `index.html` file:
   - Locate the `products` array in the JavaScript section
   - Update the product data as needed
   - Make sure to use `T12:00:00` timezone format for dates to avoid timezone issues
   - Available stages: "requirements", "development", "dten-qa", "ms-qa", "release"
   - Risk levels: "low risk", "medium", "high", "released"

3. Push changes:
   ```bash
   git add index.html
   git commit -m "[Cursor] Update product timeline data"
   git push origin gh-pages
   ```

4. Wait a few minutes for GitHub Pages to rebuild the site

## Important Notes

- All dates in the stages should include the `T12:00:00` suffix to avoid timezone issues
- The release date is displayed from the `release` stage's dates
- For products without Microsoft QA testing, simply omit the `ms-qa` stage
- The timeline automatically adjusts its width based on the earliest and latest dates
- Key features are displayed in an expandable section under each product row

## Common Tasks

1. Update a product's timeline:
   - Find the product in the `products` array by its `id`
   - Update the relevant dates in the `stages` array
   - Keep the date format as "YYYY-MM-DD"

2. Add a new product:
   - Copy an existing product object structure
   - Update all fields with the new product's information
   - Add it to the `products` array

3. Update key features:
   - Find the product in the `products` array
   - Update the `keyFeatures` array with new features

4. Change risk level:
   - Find the product in the `products` array
   - Update the `riskLevel` field with one of the available values

## Troubleshooting

- If dates are displaying incorrectly, ensure they include the `T12:00:00` suffix
- If the timeline is not showing up, check the browser console for JavaScript errors
- If changes are not reflecting on the website, make sure they were pushed to the `gh-pages` branch 