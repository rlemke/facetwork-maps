# Facetwork maps

Live, interactive maps generated end-to-end by [Facetwork](https://github.com/rlemke/facetwork)
workflows written in **FFL** (Facetwork Flow Language) and executed on the Facetwork
runtime. This repo holds only the published output; the workflows, handlers, and data
pipelines live in Facetwork and its domain packages.

### **→ View the site: https://rlemke.github.io/facetwork-maps/**

## What's here

| Section | Maps |
|---------|------|
| **Census** | A per-county **metric explorer** (13 American Community Survey metrics + a dropdown), **state rankings**, and a **Social Vulnerability Index** choropleth — all 50 states + DC, county-level. |
| **World** | **Nuclear power sites**, **major volcanoes**, and **LGBTQ+ bars & restaurants** (from OpenStreetMap), plus an **armed-conflict** country choropleth (UCDP / UNHCR / IDMC / IPC). |

Every map is self-contained (inline GeoJSON + MapLibre GL), has a **name search**, a
legend, a description, and a footer that links back to the **FFL workflow and the exact
parameters** that generated it — so each page doubles as a worked example of the platform.

## How it's published

The maps are written to object storage (MinIO/S3) by their workflows, then pushed to
GitHub Pages by another FFL workflow — `census.workflows.PublishToSite` — which walks
each storage prefix, copies the HTML into this repo, and writes the landing + section
index pages. Nothing here is edited by hand.

## Data sources

US Census Bureau (ACS 2023 + TIGER) · OpenStreetMap · UCDP (Uppsala Conflict Data
Program) · UNHCR · IDMC · IPC. See each map's footer and description for specifics.
