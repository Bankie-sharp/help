using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.EventSystems;

public class AxeHit : MonoBehaviour
{   //var
    public GameObject axe;
    private bool isEquiped = false;
    //public int hitDamage = 1;

    private void Update()
     {
        if (!axe.activeSelf && Input.GetKeyDown(KeyCode.Alpha1))
        {
            isEquiped = true;
            axe.SetActive(true);
        }
        else if (Input.GetKeyDown(KeyCode.Alpha1))
        {
            isEquiped = false;
            axe.SetActive(false);
        }


        //raycast
        Vector3 fwd = transform.TransformDirection(Vector3.forward);
        RaycastHit hit;

        if (Physics.Raycast(transform.position, fwd, out hit, 10))
        {
            if (hit.collider.tag == "tree" && Input.GetMouseButton(0) && isEquiped == true)
            {
                //Tree treeScript = hit.collider.gameObject.GetComponent<Tree>();
                //Tree treeScript = hit.collider.gameObject.GetComponent<Tree>();
                //treeScript.treeHealth -- ;
                 
                 Debug.Log(hit.transform.name);
                //Debug.Log(treeScript.treeHealth);
                // print ("Hey");
            }
        }
    }
        
    }

