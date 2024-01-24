
# V2 is based on
[https://github.com/lukin/keywind](https://github.com/lukin/keywind)

Download and extract the .Zip in the Zip you will also find some video guides

# Applying a Keycloak Theme Using the Theme Folder

In addition to deploying your Keycloak theme, you can apply the theme directly by copying the theme folder to the Keycloak installation directory. This method is useful when you prefer a simpler and more straightforward approach.

## Prerequisites

Before you begin, ensure that you meet the following requirements:

- Keycloak is already installed on your system.

## Copying the Theme Folder

1. Open a terminal and navigate to your project directory.

2. Copy the entire custom theme folder to the Keycloak themes directory using the following command:

   ```bash
   cp -r ./theme/theme /path/to/keycloak/themes/samrossiter
   ```

   Replace /path/to/keycloak with the actual path where Keycloak is installed on your system.


## Restarting Keycloak

1. Once you have copied the theme folder, you need to restart Keycloak for the changes to take effect.

   ```bash
   docker-compose restart keycloak
   ```

   This command restarts the Keycloak container, applying the newly copied theme.

## Accessing Keycloak

You can access your Keycloak instance, including the custom theme, in your web browser at the following address:

```http://localhost:8080/```

Ensure that the port 8080 matches the one you configured for your Keycloak instance.

That's it! You have successfully applied your custom Keycloak theme by copying the theme folder directly.


# Manually Applying a Keycloak Theme (By Hand)

In addition to deploying your Keycloak theme with Docker, you can manually apply the theme to Keycloak by creating a JAR file.

## Prerequisites

Before you begin, ensure that you meet the following requirements:

- Keycloak is already installed on your system.

## Creating the JAR File

1. Open a terminal and navigate to your project directory.

2. Create a JAR file containing your custom theme by executing the following command:

   ```bash
   jar -cvf samrossiter-theme.jar -C theme .
   ```

   This command packages your theme files into a JAR archive named `samrossiter-theme.jar`.

## Applying the JAR File to Keycloak

1. Determine the installation directory of Keycloak. This is typically where you have installed Keycloak on your system.

2. Navigate to the `providers` folder within your Keycloak installation directory. The full path should be:

   ```
   keycloak/providers
   ```

3. Copy the `samrossiter-theme.jar` file you created earlier and paste it into the `providers` folder.

## Rebuilding Keycloak with the New Theme

1. Open a terminal and navigate to the Keycloak installation directory.

2. Execute the following command to rebuild Keycloak with the new theme:

   ```bash
   bin/kc.sh build
   ```

   This command will recompile Keycloak, including your custom theme.

## Starting Keycloak with the Custom Theme

1. Once the build process is complete, you can start Keycloak in development mode with the following command:

   ```bash
   bin/kc.sh start-dev
   ```

   Keycloak is now running with your custom theme.

## Accessing Keycloak

You can access your Keycloak instance, including the custom theme, in your web browser at the following address:

```
http://localhost:8080/
```

Ensure that the port `8080` matches the one you configured for your Keycloak instance.

That's it! You have successfully applied and deployed your custom Keycloak theme manually.




## If something is changed in the CSS or JS file

Rename the file with a new version and update the new name in `theme.properties`, otherwise Keycloak still use the old version because of the cache, even after restarting the container on Cloudron.
