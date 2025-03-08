# Changelog
## [1.0.0] - 2025-03-08
### Create
- Menbuat Project CRUD

Old Code
    boolean insert(String nim, String nama, String alamat, int semester, int sks, double ipk){
        boolean status = true;
        //cek primary key
        if(!data.isEmpty()){
            for(int i = 0; i < data.size(); i++){
                if(data.get(i).getNim().equalsIgnoreCase(nim)){
                    status = false;
                    break;
                }
            }
        }
        if(status == true){
            Mahasiswa mhs = new Mahasiswa(nim, nama, alamat, semester, sks, ipk);
            save();
        }
        return status;
    }

New Code
// boolean insert(String nim, String nama, String alamat, int semester, int sks, double ipk){
        boolean status = true;
        //cek primary key
        if(!data.isEmpty()){
            for(int i = 0; i < data.size(); i++){
                if(data.get(i).getNim().equalsIgnoreCase(nim)){
                    status = false;
                    break;
                }
            }
        }
        if(status == true){
            Mahasiswa mhs = new Mahasiswa(nim, nama, alamat, semester, sks, ipk);
            data.add(mhs);
            save();
        }
        return status;
    }
