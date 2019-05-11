---
title: 手順 5:取引先パートナーの Web ページの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 38c3054d-932a-42b6-a821-8b30604d8426
caps.latest.revision: 38
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 149e4a2ad60cc082890b0beb8a5517142e4a27c8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244393"
---
# <a name="step-5-configure-the-trading-partner-web-pages"></a>手順 5:取引先パートナーの Web ページを構成します。
![手順 5. の 11](../core/media/tut-step5-of-11.gif "Tut_Step5_of_11")  
  
 この手順では、取引先 Web ページを設定する次のタスクを実行します。  
  
-   HTTP トランスポートに必要な BTS HTTP Receive ISAPI フィルターを有効にします。  
  
-   フォルダーと aspx ページ、パートナー組織 Fabrikam にルート、997 受信確認を設定する HTTP トランスポートを使用します。 Fabrikam 仮想ディレクトリに 997 受信確認の削除、 \\_ 997tofabrikam フォルダーは、997 送信ポートの Destination_URL の設定の説明が示されています。  
  
-   ホーム組織 Contoso に元のメッセージをルーティングする ASPX ページを設定します。 Contoso 仮想ディレクトリでは、BTSHttpReceive.dll を使用して AS2 メッセージを受信し、受信場所に送信します。  
  
> [!NOTE]
>  このトピックで説明する手順は、IIS 7.0 の場合です。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-enable-the-bts-isapi-filter"></a>BTS ISAPI フィルターを有効にするには  
  
1. クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリックします**インターネット インフォメーション サービス (IIS) マネージャー**.  
  
2. ルート Web サーバーのエントリを選択し、**機能ビュー**、 をダブルクリックします**ハンドラー マッピング**し、**アクション**ウィンドウで、をクリックして**スクリプトマップの追加**.  
  
   > [!NOTE]
   >  Web サーバー レベルでスクリプトのマッピングを構成すると、すべての子の Web サイトに適用するには、このマッピングが発生します。 特定の Web サイトまたは仮想フォルダーへのマッピングを制限する場合は、ターゲット サイトまたは Web サーバーではなくフォルダーを選択します。  
  
3. **スクリプト マップの追加** ダイアログ ボックスに、入力`BtsHttpReceive.dll`で、**要求パス**フィールド。  
  
4. **実行可能ファイル**フィールドに、をクリックして、**省略記号 (...)** ボタンをクリックしを参照する[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\HttpReceive します。 選択**BtsHttpReceive.dll**、 をクリックし、 **OK**。  
  
5. 入力`BizTalk HTTP Receive`で、`Name`フィールドをクリックして**要求の制限**します。  
  
6. **要求の制限**ダイアログ ボックスで、**動詞**タブを選び**次の動詞のいずれか**します。 入力`POST`動詞として。  
  
7. **アクセス**] タブで [**スクリプト**、順にクリックします**OK**します。  
  
8. をクリックして **[ok]** ISAPI 拡張を許可するメッセージが表示されたら、クリックと**はい**。  
  
9. BTSHttpReceive.dll エントリを右クリックし、**機能のアクセス許可の編集**します。  
  
10. いることを確認**読み取り**、**スクリプト**と**Execute**クリックして選択すると、 **OK**。  
  
11. クリックして**機能ビュー**、し、ダブルクリック**ISAPI および CGI の制限**します。  
  
12. BTSHTTPReceive.dll のエントリがあることを確認し、**制限**に設定されている**許可**します。  
  
    > [!NOTE]
    >  BTSHTTPReceive.dll ISAPI および CGI の制限のエントリは、スクリプト マップを作成するときに自動的に作成されます。  
  
### <a name="to-configure-the-fabrikam-web-page"></a>Fabrikam Web ページを構成するには  
  
1. IIS マネージャーで、右クリックして**アプリケーション プール**選択**アプリケーション プールの追加**します。  
  
2. **アプリケーション プールの追加** ダイアログ ボックスに、入力**BizTalkAppPool**で**名前**、し、 **.NET Framework v4.0.30210**で、**.NET framework のバージョン**ドロップダウン リスト。 **[OK]** をクリックします。  
  
   > [!NOTE]
   >  コンピューターにインストール済みの [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] のバージョンによって、バージョン番号が異なる場合があります。  
  
3. 選択**アプリケーション プール**の**機能ビュー**選択**BizTalkAppPool**、順にクリックします**詳細設定**で**アクション**ウィンドウ。  
  
4. **詳細設定**ダイアログ ボックスで、セット**を有効にする 32 ビット アプリケーション**に**True**します。  
  
   > [!NOTE]
   >  IIS を 32 ビット モードで実行する場合、64 ビット コンピューター上でのみこの手順が必要です。  
  
5. 選択**Identity**  をクリックし、**省略記号 (...)** ボタンをクリックします。  
  
6. **アプリケーション プール Id**ダイアログ ボックスで、**カスタム アカウント** をクリックし、**設定**します。  
  
7. 入力、**ユーザー名**と**パスワード**administrators グループのメンバーであるユーザー アカウントのパスワードを入力します**パスワードの確認入力**をクリックして **。OK** 3 回の IIS マネージャーに戻ります。  
  
8. IIS マネージャーで、開く、**サイト**フォルダー。 右クリックし、**既定の Web サイト**、し、**アプリケーションの追加**します。  
  
9. **アプリケーションの追加** ダイアログ ボックスに、入力**Fabrikam**で**エイリアス**、順にクリックします**選択**します。  
  
10. **アプリケーション プールの選択**ダイアログ ボックスで、 **BizTalkAppPool**  をクリック**OK**します。  
  
11. をクリックして、**省略記号 (...)** ボタンをクリックしを参照する[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \as2 \fabrikam、**物理パス**します。  
  
12. をクリックして**テストの設定**に表示されるエラーがないことを確認し、 **Test-connection**  ダイアログ ボックス。 **[閉じる]** をクリックし、 **[OK]** をクリックします。  
  
13. IIS マネージャーでは、Fabrikam 仮想ディレクトリを選択し、**機能ビュー**、ダブルクリック**認証**。  
  
14. **認証**を選択します**匿名認証**いることを確認し、**状態**は**有効**します。 場合、**状態**は**無効**、 をクリックして**を有効にする**で、**アクション**ウィンドウ。  
  
### <a name="to-configure-the-contoso-web-page"></a>Contoso Web ページを構成するには  
  
1. IIS マネージャーで、開く、**サイト**フォルダー。 右クリックし、**既定の Web サイト**選び**アプリケーションの追加**します。  
  
2. **アプリケーションの追加** ダイアログ ボックスに、入力**Contoso**で**エイリアス**、順にクリックします**選択**します。  
  
3. **アプリケーション プールの選択**ダイアログ ボックスで、 **BizTalkAppPool**  をクリック**OK**します。  
  
   > [!NOTE]
   >  BizTalkAppPool は Fabrikam Web ページを構成するときに以前作成された、administrators グループのメンバーであるユーザーの id に設定する必要があります。  
  
4. をクリックして、**省略記号 (...)** ボタンをクリックしを参照する[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive、**物理パス**します。  
  
5. をクリックして**テストの設定**に表示されるエラーがないことを確認し、 **Test-connection**  ダイアログ ボックス。 **[閉じる]** をクリックし、 **[OK]** をクリックします。  
  
6. IIS マネージャーでは、Contoso 仮想ディレクトリを選択し、**機能ビュー**、 をダブルクリックします**認証**します。  
  
7. **認証**を選択します**匿名認証**いることを確認し、**状態**は**有効**します。 場合、**状態**は**無効**、 をクリックして**を有効にする**で、**アクション**ウィンドウ。  
  
## <a name="next-steps"></a>次の手順  
 受信場所を構成する (**Receive_AS2**)」の説明に従って、Fabrikam から AS2 メッセージを受信する[手順 6。EDI AS2 を構成する受信場所](../core/step-6-configure-the-edi-as2-receive-location.md)します。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 3: AS2 チュートリアル](../core/tutorial-3-as2-tutorial.md)
