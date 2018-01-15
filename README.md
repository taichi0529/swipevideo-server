# swipevideo-server
Server for SwipeVideo(https://github.com/amatelus/swipevideo, https://swipevideo.jp)


# API

## GET api/new_id


Get the camera ID and index to identify the camera.
Cameras must be ordered by index.


### response

```
{
   cam_id: "0b4e7a0e5fe84ad35fb5f95b9ceeac79",
   index: 2
}
```

## GET /api/preflight/:cam_id

To prevent transmission clogging, the video is transmitted only when "enabled: true" is returned from the server.

### response

```
{
    status: "success",
    enabled: false
}
```

## POST api/origin/:cam_id

The video will be POSTed under the name "video".

### response

```
{
    status: "success"
}
```

## GET /api/battery/:cam_id/:value
For Charging control API
```
if (At charging and over 90%)　or (without charging and less than 30%) {
	Send remaining battery power
}
```

### response
```
{
    status: "success"
}
```
