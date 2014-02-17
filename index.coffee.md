NoMedia
=======

    uuid = require 'uuid'

    class NoMediaStream

      constructor: (@constraints) ->
        @id = new uuid()

        # @onended = null;
        # @onaddtrack = null;
        # @onremovetrack = null;

      get: (success,failure) ->
        success this

      setRemoteSession: (session,success,failure) ->
        success()

      stop: ->

      #  MediaStream.prototype.getAudioTracks
      #  MediaStream.prototype.getVideoTracks
      #  etc.: not implemented
      #  Doesn't look like we're using any other attribute.

      description: ->
        @constraints.description

    module.exports =
      getUserMedia: (constraints,success,failure) ->
        media = new NoMediaStream constraints
        media.get success, failure
      RTCPeerConnection: require 'rtc-peer-connection'
      RTCSessionDescription: require 'rtc-session-description'
