# API face recognition

* **Root URL demo:** `http://eye.datalab.vn`

**So sánh khuôn mặt**
------------
Trả về kết quả so sánh khuôn mặt trong hộ chiếu và ảnh chụp thực, và các tội phạm giống với ảnh chụp thực

* **URL**

    `/api/check`

* **Method**

    `POST`

* **DataForm Params**
    ```
    passport_profile_image: 'data:image....'
    real_image: 'data:image...'
    ```

* **Success response**
  * **Code:** 200
  * **Content:**
  ```
  {
    percent: 0.933234,
    passport_face: 'data:image...' // ảnh khuôn mặt tách từ hộ chiếu mã hóa base64
    real_face: 'data:image...' ảnh khuôn mặt tách từ ảnh thực
    crimes: [
        {
            id: 12,
            name: Tội phạm X,
            percent: 0.6443,
            image: 'data:image...'
        },
        {
            ...
        }
  }
  ```

**Upload tội phạm vào db**

* **URL**

    `api/crimes`

* **Method**

    `POST`

* **DataForm Params**
    ```
    name: Tên tội phạm
    image: 'data:image...' // ảnh mã hóa base64
    ```

**Xóa tội phạm trong db**
--------

Xóa tội phạm với id trong db
* **URL**
 
    `/api/crimes/:id`

* **Method**

    `DELETE

**Xem tội phạm trong db**
--------

* **URL**

    `/api/crimes`

* **Method**

    `GET`
