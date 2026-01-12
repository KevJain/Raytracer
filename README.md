![Final Render](https://github.com/KevJain/raytracer/blob/main/final.png)

This is a Raytracer written in Rust following the architecture outlined in [Peter Shirley's book](https://raytracing.github.io). Given a scene description and camera parameters (position, view target, focal length, lens radius, field of view), rays are cast from the camera through each pixel in a virtual viewport representing the final iamge. These rays are checked for intersection with objects in the scene, and if intersections are found then the colour of the ray is attenuated based on the found object and the ray is then scattered according to the object's material properties. The process is then repeated recursively until a specified max depth is reached or the ray exits the scene. Since rays are scattered using probabilistic methods based on object materials, increased samples per pixel greatly improve image quality. Samples are conducted independently and averaged, so computation is parallelized via Rayon.

It currently supports spheres and matte (Lambertian), glass-like (Dielectric), and metallic materials.

Features in progress:
- Add BVH to improve rendering times
- Add JSON support for scene description
- Add support for triangular meshes
