Cordova BarcodeScanner Plugin For Blackberry 10
===============================================

This plugin scans all types of barcodes supported by the [ZXing](https://github.com/blackberry/zxing) library. 
The Rear Camera is used and it shows the camera's viewfinder for the user to target the barcode. 

## Including the feature in your application

This API can be installed from source or from the [Cordova Plugin Registry](http://plugins.cordova.io/). Installation from the registry is done through the following:

	cordova plugin add com.blackberry.community.barcodescanner

or,
	
	webworks plugin add com.blackberry.community.barcodescanner

Installation from source is the same but instead of the id ("com.blackberry.community.barcodescanner"), use the file system path to the source plugin folder.

This feature depends on the blackberry.io which is installed with it. 

Permission for the camera is required, so a permission check will automatically be added to your application, and the user will be prompted to allow it.

When you start scanning, you can make the experience better for your users with the [Prevent Sleep Extension](https://github.com/blackberry/WebWorks-Community-APIs/tree/master/BB10-Cordova/PreventSleep). If you include Prevent Sleep in your app, the BarcodeScanner will automatically use it as needed to keep the screen on. Instructions for installing are in the Prevent Sleep [README](https://github.com/blackberry/WebWorks-Community-APIs/blob/master/BB10-Cordova/PreventSleep/README.md)

## Version History

* 1.0.0 Initial Release
* 1.0.1 Async function calls, use_camera permission inclusion, simulator .so file fix
* 1.0.2 Image Quality fix for viewfinder
* 1.0.3 Fix to read codes with spaces
* 1.0.4 Uses prefixed File API to avoid conflicts with Cordova File API
* 2.0.0 First implementation using the native Camera Viewfinder
* 2.0.1 Fixes issue with "VF Props" on 10.2.1
* 2.0.2 Resolves issue with multiple scans on 10.2.1, improves responsiveness after scan.

## Javascript API


```javascript
/* Start scanning for barcodes. 
 * @param succ
 *			Function that executes when the barcode has been recognized 
 *			successfully. Expected signature: succ(read_data), where 
 *			read_data is a string.
 * @param fail
 * 			Function that executes when the barcode has not been recognized 
 *			successfully. Expected signature: fail(error_message), 
 *			where error_message is a string.
 */
 app.barcodeScanner.startRead(succ, fail)

 /*
 * Stop scanning for barcodes.
 * @param succ
 *			Function that executes when the barcode has been stopped
 *			successfully. Expected signature: succ(stopped_notification), where 
 *			stopped_notification is a string.
 * @param fail
 * 			Function that executes when the barcode could not be 
 *			successfully stopped. Expected signature: fail(error_message), 
 *			where error_message is a string.
 */
 app.barcodeScanner.stopRead(succ, fail)

```

## License

This plugin is Open Source licensed under the [Apache 2.0 License](http://www.apache.org/licenses/LICENSE-2.0)

## Authors
[Jasmin Auger](https://github.com/FreakenK), [Alex Tough](https://github.com/alextoughg) and [Tim Windsor](https://github.com/timwindsor).

Based on code written by [Alex Kwan](https://github.com/greentea0), and [Mike Delong](https://github.com/mdelong)

## Disclaimer

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.