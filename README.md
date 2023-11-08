# Redirecting-the-scene

## Aim:
To redirect a scene using C# program in Unity engine.

## Algorithm:
Step 1: To open the unity engine.

Step 2: Create a new plane and create a cube and give color for the cube.

Step 3: Next create sphere in the orgin and change the z-axis and Give the color for the sphere.

Step 4: Create a tag for the Sphere and Make the sphere and cube as a Rigidbodies and Make the sphere use Gravity.

Step 5: Create the C# script file in the Assets and write the Coding for the Redirecting to the scene1 after hit the sphere to cube.

Step 6: Next Create a another new scene named as scene1.

Step 7: In File->Build settings and drop the both first scene and scene1 scene in the Scenes in build setting.

Step 8: Click the Build and run button in the Build settings and run the scene.

Step 9: The Sphere after touching the cube it will disappeared and Press the key [R] the redircting to the new scene that is scene1.

## Program:
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.SceneManagement;

public class Player : MonoBehaviour
{
    public GameObject WinText;
    Rigidbody rb;

    // Start is called before the first frame update
    public void Start()
    {
        rb = GetComponent<Rigidbody>();
    }

    // Update is called once per frame
    public void Update()
    {
        if (Input.GetKeyDown(KeyCode.Space))
            SceneManager.LoadScene("SampleScene");
        
    }
    private void OnMouseDown()
    {
        Destroy(gameObject);
    }
    public void OnCollisionEnter(Collision collision)
    {
        if (collision.gameObject.tag=="Sphere")
        {
            Destroy(collision.gameObject);
            WinText.SetActive(true);
        }
    }
}
```
## Output:
![image](https://github.com/kaviya2839/Redirecting-the-scene/assets/120553351/29ac766b-ce7c-460a-80e4-9cda1034f626)

![image](https://github.com/kaviya2839/Redirecting-the-scene/assets/120553351/0fada142-5259-4a12-8add-abd8e987934c)


## Result:
Thus, a scene is redirected in Unity engine using a C# program.
