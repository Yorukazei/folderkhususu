import java.util.Scanner; // Mengimpor kelas Scanner dari Java untuk mengambil input dari pengguna
public class UasAtlet { //Mendeklarasikan kelas bernama UsaAtlet
    public static void main(String[] args) { //Metode utama yang akan dieksekusi pertama kali saat program dijalankan
        Scanner sc = new Scanner(System.in); //Membuat objek Scanner untuk menerima input dari pengguna melalui keyboard

        System.out.print("Masukkan jumlah politeknik (harus lebih dari 0): "); //Menampilkan pesan kepada pengguna untuk memasukkan jumlah politeknik
        int jumlahPoliteknik = sc.nextInt(); //Menerima input jumlah politeknik dari pengguna
        sc.nextLine(); //Membersihkan buffer setelah pemakaian nextInt()
        
        if (jumlahPoliteknik <= 0) { //Jika jumlah politeknik yang dimasukkan kurang dari atau sama dengan nol, program akan menampilkan pesan error dan keluar (return)
            System.out.println("Jumlah politeknik tidak valid.");
            return; 
        }

        String[][][] atlet = new String[3][jumlahPoliteknik][3]; //adalah array 3 dimensi untuk menyimpan nama atlet berdasarkan cabang olahraga, politeknik, dan nomor atlet.
        String[] cabor = {"Badminton", "Basket", "Bola Voli"}; //adalah array berisi daftar cabang olahraga.

        for (int olahraga = 0; olahraga < cabor.length; olahraga++) { //Loop pertama untuk iterasi setiap cabang olahraga.

            System.out.println("Masukkan nama atlet untuk cabang " + cabor[olahraga] + ":"); //Menampilkan pesan untuk meminta input nama atlet sesuai cabang olahraga.
            for (int politeknik = 0; politeknik < jumlahPoliteknik; politeknik++) { //Loop kedua untuk iterasi setiap politeknik.
                System.out.println("Politeknik " + (politeknik + 1) + ":"); //Menampilkan politeknik yang sedang diinput.
                for (int nama = 0; nama < 3; nama++) { //Loop ketiga untuk iterasi setiap atlet dalam satu politeknik.
                    System.out.print("Atlet " + (nama + 1) + ": "); //Meminta pengguna memasukkan nama atlet.
                    String namaAtlet = sc.nextLine();
                    
                    if (namaAtlet.isEmpty()) { //Jika nama atlet kosong, menampilkan pesan kesalahan dan mengulang input, Jika tidak kosong, menyimpan nama atlet dalam array atlet.
                        System.out.println("Nama atlet tidak boleh kosong. Silakan masukkan kembali.");
                        nama--;
                    } else {
                        atlet[olahraga][politeknik][nama] = namaAtlet; //Menyimpan nama atlet yang valid ke dalam array atlet berdasarkan cabang olahraga, politeknik, dan nomor urut atlet.
                    }
                }
            }
        }

        System.out.println("\nInformasi Nama Atlet:"); //Menampilkan header untuk informasi yang akan ditampilkan.
        for (int olahraga = 0; olahraga < cabor.length; olahraga++) { //Loop untuk menampilkan data atlet berdasarkan cabang olahraga.
            System.out.println("Cabang " + cabor[olahraga] + ":"); //Menampilkan nama cabang olahraga. //Loop untuk menampilkan data politeknik.
            for (int politeknik = 0; politeknik < jumlahPoliteknik; politeknik++) { //Menampilkan nama atlet berdasarkan indeksnya.
                System.out.println("Politeknik " + (politeknik + 1) + ":"); //Menampilkan informasi tentang politeknik yang sedang diproses dalam iterasi.
                for (int nama = 0; nama < 3; nama++) { //Loop ketiga untuk mengiterasi setiap atlet dalam politeknik tersebut.
                    System.out.println("Atlet " + (nama + 1) + ": " + atlet[olahraga][politeknik][nama]); //mengambil nama atlet yang tersimpan dalam array tiga dimensi.

                }
                System.out.println();
            }
        }
    }
}