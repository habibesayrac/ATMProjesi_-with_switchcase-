# ATMProjesi_-with_switchcase-

import java.util.Scanner;

public class Main {

    public static void main(String[] args) {
        String userName, password;
        Scanner input = new Scanner(System.in);
        int right = 3;
        int balance = 1500;
        int select;

        while (right > 0) {
            System.out.print("Kullanıcı Adınız:  ");
            userName = input.nextLine();
            System.out.print("Parolanız:  ");
            password = input.nextLine();
            if (userName.equals("patika") && password.equals("dev123")) {
                System.out.println("Merhaba X Bankasına Hoşgeldiniz!");
                do {
                    System.out.println("Lütfen yapmak istediğiniz işlemi seçiniz.");
                    System.out.println("1-Para Yatırma\n" +
                            "2-Para Çekme\n" +
                            "3-Bakiye Sorgula\n" +
                            "4-Çıkış Yap");
                    select = input.nextInt();
                    switch (select) {
                        case 1:
                            System.out.print("Para miktarı: ");
                            int price = input.nextInt();
                            balance += price;
                            System.out.println("Toplam Bakiye: " + balance);
                            break;
                        case 2:
                            System.out.print("Para miktarı :");
                            int price1 = input.nextInt();
                            if (price1 > balance) {
                                System.out.println("Bakiye yetersiz.");
                            } else {
                                balance -= price1;
                            }
                            break;
                        case 3:
                            System.out.println("Bakiyeniz: " + balance);
                            break;
                    }
                } while (select != 4);
                break;
            } else {
                right--;
                System.out.println("Hatalı kullanıcı adı veya şifre. Tekrar deneyiniz.");
                if (right == 0) {
                    System.out.println("Hesabınız bloke olmuştur, lütfen banka ile iletişime geçiniz.");
                    break;
                }
                System.out.println("Kalan hakkınız: " + right);
            }
        }
    }
}
