oscp5
=====

An Open Sound Control (OSC) implementation for java and processing.org. Download latest .zip from [releases](https://github.com/trackme518/oscp5/releases). Since original library is not maintained anymore (last update around 2015) I did some edits in my fork to suit my needs, feel free to use it. 

## Updates
By https://github.com/trackme518 :

* fixed bug on Linux with OSC broadcast
* exposed sender ip address with new function `.getIP()` - returns IP as a String (ie "168.0.4.2")
* modified the library so you can have multiple apps listening on the same port (currently working for UdpServer version only )
* changed return type of send() function from void to boolean to indicate success / failure (in OscP5.java)
* added new function oscP5.isServerRunning() to indicate if the udp server is listening or failed

```
public String getIP( ) {
	return hostAddress;//Bytes.getAsString( hostAddress );
}
```
In OscMessage.java

```
channel.socket().setBroadcast(true);
```
&
```
channel.socket( ).setReuseAddress(true);
```
In UdpServer.java

```
public boolean isServerRunning(){
...//points to instance of udpserver of internal server of thread isAlive() function
}
```
In UdpServer.java & OscP5.java
