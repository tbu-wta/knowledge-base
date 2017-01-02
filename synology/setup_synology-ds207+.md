# Synology DS207+

## Requirements

 ### Software
  * [Synology Assistant](https://www.synology.com/en-global/support/download)
  * [DSM](https://www.synology.com/en-global/support/download)

## Basic Setup
 1. Install Synology Assistant 
  * Make sure, the download page really lists the newest version
  * If no device is found, temporarily deactivate firewall or add exception for Synology Assistant
  * If set up with One-Click Setup, the admin password will be blank
 1. Install DSM (via Synology Assistant)

## Connect to Synology DSM via 
 1. Use Synology Assistant
 1. Use web browser
  * http://Synology_Server_IP:5000
  * http://Synology_Server_Name:5000/
  * f set up with One-Click Setup, the server name will be DiskStation
 1. Create Drive <!-- LINK TO THIS SECTION OF THE TUTORIAL -->

## Set Up Hard Drives
 1. Create Disc Group
 1. Create Volumes

 ### RAID Types
  * Synology Hybrid RAID (SHR)
   * Wiht data protection
   * Optimize storage capacity when combining hard drives with different sizes
   * data integrity is protected, when one of the (2-3) hard drives fails
  * RAID 1
   * With data proteciton
   * write identical data to each harddrive at the same time
   * data integrity is protected, when at least one drive is normal
  * JBOD
   * Without data protection
   * collection of hard drives
   * higher probability of restoring some data if one drive fails
  * RAID 0
   * Without data proteciton
   * combine multiple hard drives to create one storage space
   * Provides stripping (spreads blocks across drives)
   * small probability of restoring some data if one drive fails

## Set Up Static IP

## 

## Connect via NFS



## SSL Certoficat with [Let’s Encrypt](https://letsencrypt.org/)

## Further Resources
 * [Synology Web Assistant](http://find.synology.com/) did not work, maybe due to firewall...?