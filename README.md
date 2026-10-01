# Последняя комбинация — client test

Static Russian-language investigation quiz. Serve the repository root as a static site, or open `index.html` locally. No build step is required.

The client package includes the provided case materials but excludes the instructor scenario document. The answer key is present in `scenario-data.js` because this is a client-side quiz; do not use browser-side scoring for a secure examination.

The supplied scenario has 20 fully specified interactive stages; its route map additionally names O-02 without providing a question or answer choices. The greeting uses a new illustrated instructor and leads to a short silent case intro. See `CLIENT_HANDOFF.md` for outstanding content and review items.

## GitHub and Vercel

1. Create a **private** empty GitHub repository named `police-academy-quiz` (do not initialize it with a README).
2. From this extracted folder run:

   ```bash
   git init
   git add .
   git commit -m "Client test version"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/police-academy-quiz.git
   git push -u origin main
   ```

3. In Vercel, select **Add New → Project**, import that GitHub repository, set the framework preset to **Other**, leave the build command empty and output directory at the repository root, then deploy.
4. Share the Vercel preview URL with the client. All PDFs in `materials/` can be opened by anyone who has the deployed URLs; use Vercel deployment protection if the case documents should have restricted access.
