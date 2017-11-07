---
title: "手順 5: 取引先の Web ページの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 38c3054d-932a-42b6-a821-8b30604d8426
caps.latest.revision: "38"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3f1dce6a68dc334f9f5f30b1aae938ada6f612a
ms.sourcegitcommit: 9aaed443492b74729171fef79c634bff561af929
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2017
---
# <a name="step-5-configure-the-trading-partner-web-pages"></a>手順 5: 取引先の Web ページを構成します。
![手順 5. 11 の](../core/media/tut-step5-of-11.gif "Tut_Step5_of_11")  
  
 ここでは、次の作業を実行して取引先の Web ページを設定します。  
  
-   HTTP トランスポートに必要な BTS HTTP Receive ISAPI フィルターを有効にします。  
  
-   997 受信確認を HTTP トランスポートを使用してパートナー組織 Fabrikam にルーティングするように、フォルダと aspx ページを設定します。 Fabrikam 仮想ディレクトリに 997 受信確認の削除、 \\_ 997tofabrikam フォルダーは、997 送信ポートの Destination_URL の設定で呼び出されます。  
  
-   元のメッセージをホーム組織 Contoso にルーティングするように ASPX ページを設定します。 Contoso 仮想ディレクトリは、BTSHttpReceive.dll を使用して AS2 メッセージを受信し、それを受信場所に送信します。  
  
> [!NOTE]
>  このトピックで説明している手順は IIS 7.0 の場合の手順です。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-enable-the-bts-isapi-filter"></a>BTS ISAPI フィルターを有効にするには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、クリックして**インターネット インフォメーション サービス (IIS) マネージャー**.  
  
2.  Web サーバーのエントリのルートを選択し、[、**機能ビュー**をダブルクリックして**ハンドラー マッピング**し、**アクション**] ウィンドウで、をクリックして**スクリプトマップの追加**.  
  
    > [!NOTE]
    >  Web サーバー レベルでスクリプトのマッピングを構成すると、すべての子 Web サイトにこのマッピングが適用されます。 特定の Web サイトまたは仮想フォルダーへのマッピングを制限する場合は、ターゲット サイトまたは Web サーバーではなくフォルダーを選択します。  
  
3.  **スクリプト マップの追加** ダイアログ ボックスで、入力`BtsHttpReceive.dll`で、**要求パス**フィールドです。  
  
4.  **実行可能ファイル**フィールドで、をクリックして、**省略記号 (...)**ボタンをクリックしを参照[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\HttpReceive です。 選択**BtsHttpReceive.dll**、順にクリック**OK**です。  
  
5.  入力`BizTalk HTTP Receive`で、`Name`フィールドをクリックして**要求の制限**です。  
  
6.  **要求の制限**ダイアログ ボックスで、**動詞**タブをクリックし**次の動詞のいずれかの**します。 入力`POST`動詞として。  
  
7.  **アクセス**] タブで [**スクリプト**、クリックして**[ok]**です。  
  
8.  をクリックして**OK** ISAPI 拡張を許可するメッセージが表示されたらをクリックし、**はい**です。  
  
9. BTSHttpReceive.dll エントリを右クリックし、**機能のアクセス許可を編集**です。  
  
10. いることを確認**読み取り**、**スクリプト**と**Execute**が選択されていると、をクリックして**OK**です。  
  
11. をクリックして**機能ビュー**、順にダブルクリック**ISAPI および CGI の制限**です。  
  
12. BTSHTTPReceive.dll のエントリがあることを確認し、**制限**に設定されている**許可**です。  
  
    > [!NOTE]
    >  BTSHTTPReceive.dll の [ISAPI および CGI の制限] のエントリは、スクリプト マップの作成時に自動的に作成されます。  
  
### <a name="to-configure-the-fabrikam-web-page"></a>Fabrikam Web ページを構成するには  
  
1.  IIS マネージャーを右クリックして**アプリケーション プール**選択**アプリケーション プールの追加**です。  
  
2.  **アプリケーション プールの追加**] ダイアログ ボックスで、入力**BizTalkAppPool**で**名前**、し、[ **.NET Framework V4.0.30210**で、**.NET framework のバージョン**ドロップダウン リスト。 **[OK]**をクリックします。  
  
    > [!NOTE]
    >  コンピューターにインストール済みの [!INCLUDE[netfx40_short](../includes/netfx40-short-md.md)] のバージョンによって、バージョン番号が異なる場合があります。  
  
3.  選択**アプリケーション プール**の**機能ビュー**選択**BizTalkAppPool**、順にクリック**詳細設定**で**アクション**ウィンドウです。  
  
4.  **詳細設定**ダイアログ ボックスで、セット**を有効にする 32 ビット アプリケーション**に**True**です。  
  
    > [!NOTE]
    >  この手順は、64 ビットのコンピューター上で IIS を 32 ビット モードで実行する場合にのみ必要です。  
  
5.  選択**Identity**をクリックし、**省略記号 (...)**ボタンをクリックします。  
  
6.  **アプリケーション プール Id**ダイアログ ボックスで、**カスタム アカウント** をクリックし、**設定**です。  
  
7.  入力、**ユーザー名**と**パスワード**administrators グループのメンバーであるユーザー アカウントのパスワードを入力で**パスワードの確認入力**をクリックして**OK** IIS マネージャーに戻りますを 3 回です。  
  
8.  IIS マネージャーで、開く、**サイト**フォルダーです。 右クリックし、 **Default Web Site**、し、**アプリケーションの追加**です。  
  
9. **アプリケーションの追加** ダイアログ ボックスで、入力**Fabrikam**で**エイリアス**、順にクリック**選択**です。  
  
10. **アプリケーション プールの選択**ダイアログ ボックスで、 **BizTalkAppPool**  をクリック**OK**です。  
  
11. クリックして、**省略記号 (...)**ボタンをクリックしを参照[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \as2 \fabrikam に移動、**物理パス**です。  
  
12. をクリックして**テストの設定**に表示されるエラーがないことを確認し、**接続のテスト** ダイアログ ボックス。 **[閉じる]**をクリックし、 **[OK]**をクリックします。  
  
13. IIS マネージャーで、Fabrikam 仮想ディレクトリを選択し、**機能ビュー**をダブルクリックして**認証**です。  
  
14. **認証**を選択**匿名認証**ことを確認し、**ステータス**は**有効**です。 場合、**ステータス**は**無効になっている**、 をクリックして**を有効にする**で、**アクション**ウィンドウです。  
  
### <a name="to-configure-the-contoso-web-page"></a>Contoso Web ページを構成するには  
  
1.  IIS マネージャーで、開く、**サイト**フォルダーです。 右クリックし、 **Default Web Site**し、**アプリケーションの追加**です。  
  
2.  **アプリケーションの追加** ダイアログ ボックスで、入力**Contoso**で**エイリアス**、順にクリック**選択**です。  
  
3.  **アプリケーション プールの選択**ダイアログ ボックスで、 **BizTalkAppPool**  をクリック**OK**です。  
  
    > [!NOTE]
    >  BizTalkAppPool は以前に Fabrikam Web ページを構成したときに作成されており、管理者グループのメンバーであるユーザーの ID に設定されています。  
  
4.  クリックして、**省略記号 (...)**ボタンをクリックしを参照[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HttpReceive、**物理パス**です。  
  
5.  をクリックして**テストの設定**に表示されるエラーがないことを確認し、**接続のテスト** ダイアログ ボックス。 **[閉じる]**をクリックし、 **[OK]**をクリックします。  
  
6.  IIS マネージャーでは、Contoso 仮想ディレクトリを選択し、、**機能ビュー**をダブルクリックして**認証**です。  
  
7.  **認証**を選択**匿名認証**ことを確認し、**ステータス**は**有効**です。 場合、**ステータス**は**無効になっている**、 をクリックして**を有効にする**で、**アクション**ウィンドウです。  
  
## <a name="next-steps"></a>次の手順  
 受信場所を構成する (**Receive_AS2**)」の説明に従って、Fabrikam から AS2 メッセージを受信する[手順 6: EDI、AS2 の受信場所を構成する](../core/step-6-configure-the-edi-as2-receive-location.md)です。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 3: AS2 チュートリアル](../core/tutorial-3-as2-tutorial.md)
