# Indentation for the new control flow

1. Install Prettier as a Dev Dependency

   ```bash
   npm i -D prettier
   ```

2. Add a `.prettierrc` file
   Then, create a `.prettierrc` file in your project's root with the folowing settings:

   ```json
   {
     "overrides": [
       {
         "files": "*.html",
         "options": {
           "parser": "angular"
         }
       }
     ]
   }
   ```

3. Restart

   Restart Visual Studio Code to start using the new configuration.
