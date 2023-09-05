

Unexpected error from cudaGetDeviceCount(). Did you run some cuda functions before calling NumCudaDevices() that might have already set an error? Error 804: forward compatibility was attempted on non supported HW
Starting LLM API Service...
>> Waiting for LLM API Service to start up.
Starting Chatchat API Service...
>> Waiting for Chatchat API Service to start up.
>> Waiting for Chatchat API Service to start up.
Starting WebUI Service...

  You can now view your Streamlit app in your browser.

  Network URL: http://172.17.0.3:8501
  External URL: http://113.207.111.143:8501
**********************************************************
2023-09-05 12:00:12,865 - _client.py[line:1013] - INFO: HTTP Request: POST http:                                           //127.0.0.1:7861/chat/knowledge_base_chat "HTTP/1.1 200 OK"
2023-09-05 12:00:20.315 Uncaught app exception
Traceback (most recent call last):
  File "/usr/local/lib/python3.10/dist-packages/httpcore/_exceptions.py", line 1                                           0, in map_exceptions
    yield
  File "/usr/local/lib/python3.10/dist-packages/httpcore/_sync/http11.py", line                                            197, in _receive_event
    event = self._h11_state.next_event()
  File "/usr/local/lib/python3.10/dist-packages/h11/_connection.py", line 469, i                                           n next_event
    event = self._extract_next_receive_event()
  File "/usr/local/lib/python3.10/dist-packages/h11/_connection.py", line 419, i                                           n _extract_next_receive_event
    event = self._reader.read_eof()  # type: ignore[attr-defined]
  File "/usr/local/lib/python3.10/dist-packages/h11/_readers.py", line 204, in r                                           ead_eof
    raise RemoteProtocolError(
h11._util.RemoteProtocolError: peer closed connection without sending complete m                                           essage body (incomplete chunked read)

The above exception was the direct cause of the following exception:

Traceback (most recent call last):
  File "/usr/local/lib/python3.10/dist-packages/httpx/_transports/default.py", l                                           ine 60, in map_httpcore_exceptions
    yield
  File "/usr/local/lib/python3.10/dist-packages/httpx/_transports/default.py", l                                           ine 104, in __iter__
    for part in self._httpcore_stream:
  File "/usr/local/lib/python3.10/dist-packages/httpcore/_sync/connection_pool.p                                           y", line 347, in __iter__
    for part in self._stream:
  File "/usr/local/lib/python3.10/dist-packages/httpcore/_sync/http11.py", line                                            325, in __iter__
    raise exc
  File "/usr/local/lib/python3.10/dist-packages/httpcore/_sync/http11.py", line                                            317, in __iter__
    for chunk in self._connection._receive_response_body(**kwargs):
  File "/usr/local/lib/python3.10/dist-packages/httpcore/_sync/http11.py", line                                            186, in _receive_response_body
    event = self._receive_event(timeout=timeout)
  File "/usr/local/lib/python3.10/dist-packages/httpcore/_sync/http11.py", line                                            196, in _receive_event
    with map_exceptions({h11.RemoteProtocolError: RemoteProtocolError}):
  File "/usr/lib/python3.10/contextlib.py", line 153, in __exit__
    self.gen.throw(typ, value, traceback)
  File "/usr/local/lib/python3.10/dist-packages/httpcore/_exceptions.py", line 1                                           4, in map_exceptions
    raise to_exc(exc) from exc
httpcore.RemoteProtocolError: peer closed connection without sending complete me                                           ssage body (incomplete chunked read)

The above exception was the direct cause of the following exception:

Traceback (most recent call last):
  File "/usr/local/lib/python3.10/dist-packages/streamlit/runtime/scriptrunner/s                                           cript_runner.py", line 552, in _run_script
    exec(code, module.__dict__)
  File "/langchain-ChatGLM-dev/webui.py", line 57, in <module>
    pages[selected_page]["func"](api)
  File "/langchain-ChatGLM-dev/webui_pages/dialogue/dialogue.py", line 112, in d                                           ialogue_page
    for d in api.knowledge_base_chat(prompt, selected_kb, kb_top_k, history):
  File "/langchain-ChatGLM-dev/webui_pages/utils.py", line 211, in _httpx_stream                                           2generator
    for chunk in r.iter_text(None):
  File "/usr/local/lib/python3.10/dist-packages/httpx/_models.py", line 844, in                                            iter_text
    for byte_content in self.iter_bytes():
  File "/usr/local/lib/python3.10/dist-packages/httpx/_models.py", line 823, in                                            iter_bytes
    for raw_bytes in self.iter_raw():
  File "/usr/local/lib/python3.10/dist-packages/httpx/_models.py", line 881, in                                            iter_raw
    for raw_stream_bytes in self.stream:
  File "/usr/local/lib/python3.10/dist-packages/httpx/_client.py", line 123, in                                            __iter__
    for chunk in self._stream:
  File "/usr/local/lib/python3.10/dist-packages/httpx/_transports/default.py", l                                           ine 103, in __iter__
    with map_httpcore_exceptions():
  File "/usr/lib/python3.10/contextlib.py", line 153, in __exit__
    self.gen.throw(typ, value, traceback)
  File "/usr/local/lib/python3.10/dist-packages/httpx/_transports/default.py", l                                           ine 77, in map_httpcore_exceptions
    raise mapped_exc(message) from exc
httpx.RemoteProtocolError: peer closed connection without sending complete messa                                           ge body (incomplete chunked read)
2023-09-05 12:00:32,437 - _client.py[line:1013] - INFO: HTTP Request: POST http:                                           //127.0.0.1:7861/chat/chat "HTTP/1.1 200 OK"
2023-09-05 12:04:14,143 - _client.py[line:1013] - INFO: HTTP Request: POST http://127.0.0.1:7861/chat/chat "HTTP/1.1 200 OK"
2023-09-05 12:04:44.181 Uncaught app exception
Traceback (most recent call last):
  File "/usr/local/lib/python3.10/dist-packages/streamlit/runtime/scriptrunner/script_runner.py", line 552, in _run_script
    exec(code, module.__dict__)
  File "/langchain-ChatGLM-dev/webui.py", line 57, in <module>
    pages[selected_page]["func"](api)
  File "/langchain-ChatGLM-dev/webui_pages/dialogue/dialogue.py", line 104, in dialogue_page
    chat_box.update_msg(text, streaming=False)  # 更新最终的字符串，去除光标
  File "/usr/local/lib/python3.10/dist-packages/streamlit_chatbox/messages.py", line 191, in update_msg
    old_element = self.history[history_index]["elements"][element_index]
  File "/usr/local/lib/python3.10/dist-packages/streamlit_chatbox/messages.py", line 64, in history
    return st.session_state.get(self._session_key).get(self._chat_name)
AttributeError: 'NoneType' object has no attribute 'get'

