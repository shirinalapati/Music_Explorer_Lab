# Music Explorer — Personalized Music Discovery

## Authors

- Shirin Alapati
- Solo project for CS 133 (Introduction to Data Visualization) at San José State University.
- Both the Data Collection and Storage Plan and the Data Analysis and Visualization Plan are written by Shirin Alapati, who is responsible for both planning sections.

## Project Description

Music Explorer will be an interactive web application that helps users discover songs based on a selection of tracks they already enjoy. The project will collect, clean, and integrate appropriately licensed music metadata and features to explore relationships among songs, artists, and genres. Machine learning methods will rank similar tracks, while interactive visualizations will help users understand the characteristics behind each recommendation. Users will be able to enter favorite songs from the supported catalog, and an optional Spotify integration will exclude tracks already saved in their Liked Songs if developer access and platform terms permit. The final deliverable will include a deployed web application, reproducible data-processing code, statistical analysis, and an evaluation of recommendation quality, diversity, and dataset limitations.

## Project Outline / Plan

- Build a verified, documented song catalog from licensed sources.
- Analyze and visualize song features, genres, and catalog coverage.
- Develop and compare recommendation approaches, starting from a simple baseline.
- Deliver an accessible interactive web application that explains its recommendations.
- Evaluate recommendation quality, diversity, and limitations honestly.

### Interface Plan

- A searchable catalog where users will select several favorite songs.
- A ranked recommendation list showing artist and title, with explanations based only on the features actually available in the final dataset.
- Controls for balancing similarity versus variety, plus an option to exclude the selected songs or their artists from results.
- An interactive song-similarity map with linked feature comparisons between selected songs and recommendations.
- Links to listen on an external music service when such links are available.
- An optional Spotify connection for filtering out tracks already saved by the user.
- A public demonstration that will remain fully usable without a Spotify login.
- Planned web deployment with an accessible, responsive interface (keyboard navigation, readable contrast, labeled controls).
- Proposed stack: a Python backend and a React frontend with Plotly visualizations; these implementation choices are provisional and may change as the project develops.

### Data Collection and Storage Plan — Shirin Alapati

- Evaluate candidate sources such as MusicBrainz metadata and appropriately licensed music-feature or listening datasets.
- Verify licensing, downloadable access, useful fields, join identifiers, and catalog coverage before selecting the final datasets.
- Integrate at least two compatible sources where feasible; integrating additional sources is a project goal rather than a guarantee.
- Spotify will not be assumed to supply audio features, recommendations, unrestricted access, or a complete training dataset.
- Audit row counts, data types, missingness, duplicates, inconsistent artist/title names, and catalog coverage.
- Match records using stable identifiers (for example, MusicBrainz IDs or ISRCs) where available, and document uncertain or fuzzy matches.
- Keep raw data snapshots separate from cleaned data.
- Store analytical data as CSV/Parquet and use SQLite initially for searchable metadata.
- Provide a data dictionary, source attribution, and documented cleaning decisions.
- Keep secrets, OAuth tokens, personal library data, large datasets, and restricted assets out of Git.
- Use reproducible download and processing scripts instead of committing large datasets.
- Spotify integration is optional and subject to current developer-access limits.
- Spotify-derived content will not be used to train, or as input to, any machine learning model. The proposed saved-song exclusion will be an ordinary filtering step, separate from the independently sourced recommendation model, and subject to verification of platform terms.

### Data Analysis and Visualization Plan — Shirin Alapati

- Summarize dataset coverage and the distributions of available song features.
- Analyze relationships among features and how they vary across represented genres.
- Conduct at least one justified statistical test, such as a one-way ANOVA or a Kruskal–Wallis test for an available numeric feature across genre groups, chosen according to whether assumptions hold; report effect sizes and limitations.
- Create at least five static visualizations: catalog coverage, feature distributions, feature relationships, genre comparisons, and recommendation evaluation.
- Explain each chart choice and use accessible color palettes and clear labels.
- Build an interactive similarity map with linked comparisons, noting that a two-dimensional projection is only an approximation of high-dimensional similarity.
- Start with a simple recommendation baseline (such as popularity or genre matching), then compare a content-based nearest-neighbor approach and at least one learned-representation or hybrid approach if the data supports it.
- Evaluate recommendations using held-out user interactions if available; otherwise, run a clearly described small user-rating study and acknowledge its limitations.
- Measure relevance, diversity, and catalog coverage; feature similarity alone will not be treated as equivalent to user satisfaction.
- Discuss popularity bias, missing metadata, catalog coverage gaps, subjective taste, and the limited generalizability of tester feedback.

### Milestones and Deliverables

- Source selection, data dictionary, and initial quality audit.
- Cleaned dataset, documented cleaning decisions, and statistical analysis.
- At least five static visualizations with design rationale and bias critique.
- Interactive dashboard prototype, peer feedback, and revision plan.
- Recommendation-model comparison and evaluation.
- Deployed application, reproducible documentation, final report, and eight-minute presentation.

### Scope and Limitations

- Core scope: recommendations and visual exploration within a verified, supported catalog.
- Spotify account connection is an optional extension and will not be required to use the core app.
- A student development integration may be limited to authorized testers; public deployment does not imply unrestricted Spotify login.
- Recommendations will not cover every commercial song, and the app will not claim that an unsaved song has never been heard by the user.
- Final dataset choices and model complexity will depend on access, licensing, coverage, and evaluation results.

## License

The MIT License in [LICENSE](LICENSE) covers the original project code and documentation in this repository. Third-party data and metadata retain their own licenses and terms of use, which will be documented with source attribution.
