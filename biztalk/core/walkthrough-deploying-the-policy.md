---
title: 'チュートリアル: ポリシーの展開 |Microsoft Docs'
ms.custom: ''
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 205760e2-9cd4-496f-93cd-0f93bc5d3231
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99c44b8104cd17cba5430b36bf1a2aa4144f2b60
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392385"
---
# <a name="walkthrough-deploying-the-policy"></a>チュートリアル: ポリシーの展開
このチュートリアルを展開するための手順について説明します、 **ProcessPurchaseOrder**次の 3 つの方法でポリシー。  
  
-   エクスポートして、ビジネス ルール エンジン展開ウィザードを使用して、ポリシーをインポートします。  
  
-   XML ファイルと XML ファイルから BizTalk Server 管理コンソールを使用して、ポリシーをインポートするには、ポリシーをエクスポートします。  
  
-   MSI ファイルの一部として、ポリシーをエクスポートし、BizTalk Server 管理コンソールを使用して MSI ファイルをインポートします。  
  
## <a name="prerequisites"></a>前提条件  
 完了する必要があります、[チュートリアル。ポリシー実行の追跡](../core/walkthrough-tracking-policy-execution.md)このチュートリアルを実行する前にチュートリアル。  
  
## <a name="overview-of-this-walkthrough"></a>このチュートリアルの概要  
 このトピックには、次の 3 つのチュートリアルが含まれています。  
  
1.  最初のチュートリアルには展開手順が含まれています、 **ProcessPurchaseOrder**ビジネス ルール エンジン展開ウィザードを使用してポリシー。 次の表では、このチュートリアルの手順について説明します。  
  
    |プロシージャ タイトル|手順の説明|  
    |---------------------|---------------------------|  
    |ビジネス ルール エンジン展開ウィザードを使用して POVocabulary 1.0 および 1.1 をエクスポートするには|バージョン 1.0 および 1.1 をエクスポートするための手順について説明します、 **POVocabulary**ボキャブラリを XML には、ビジネス ルール エンジン展開ウィザードを使用してファイルします。|  
    |ビジネス ルール エンジン展開ウィザードを使用して ProcessPurchaseOrder 1.3 をエクスポートするには|バージョン 1.3 をエクスポートするための手順について説明します、 **ProcessPurchaseOrder**ビジネス ルール エンジン展開ウィザードを使用して XML ファイルにポリシー。|  
    |ProcessPurchaseOrder および POVocabulary を削除するには|削除するための手順について説明します、 **ProcessPurchaseOrder**ポリシーと**POVocabulary**ボキャブラリを再作成するファイル、XML のインポートをテストできるようにします。|  
    |POVocabulary 1.0 および 1.1 を再作成する XML からインポートするには|再作成する最初の手順で作成したボキャブラリ XML ファイルをインポートするための手順を提供します、 **POVocabulary**ボキャブラリです。|  
    |確認するには、その POVocabulary 1.0 および 1.1 が再作成されます。|ビジネス ルール作成ツールを使用して検証するための手順は、のバージョン 1.0 および 1.1 **POVocabulary**は再作成します。|  
    |ProcessPurchaseOrder 1.3 を再作成する XML からインポートするには|バージョン 1.3 を再作成する 2 番目の手順で作成したポリシー XML ファイルをインポートするための手順を提供します、 **ProcessPurchaseOrder**ポリシー。|  
    |ProcessPurchaseOrder 1.3 が再作成されたことを確認するには|ビジネス ルール作成ツールを使用して、バージョン 1.3 を検証するための手順について説明します、 **ProcessPurchaseOrder**ポリシーが再作成されます。|  
  
2.  2 番目のチュートリアルには展開手順が含まれています、 **ProcessPurchaseOrder**次の BizTalk Server 管理コンソールからエクスポートされたポリシー XML ファイルを使用してテーブルには、この手順がについて説明しますチュートリアルです。  
  
    |プロシージャ タイトル|手順の説明|  
    |---------------------|---------------------------|  
    |ProcessPurchaseOrder 1.3 ポリシーと POVocabulary ボキャブラリを XML ファイルにエクスポートするには|BizTalk Server 管理コンソールを使用してエクスポートする手順について説明します、 **ProcessPurchaseOrder**ポリシーと**POVocabulary**ボキャブラリを XML ファイルにします。|  
    |ProcessPurchaseOrder ポリシーを削除するには|削除するための手順について説明します、 **ProcessPurchaseOrder**からポリシー **RuleTestApp**とルール エンジン データベース。|  
    |ProcessPurchaseOrder ポリシーを再作成する XML ファイルをインポートするには|再作成する最初の手順でエクスポートした XML ファイルをインポートするための手順を提供します、 **ProcessPurchaseOrder**ポリシー。|  
    |RuleTestApp アプリケーションに ProcessPurchaseOrder ポリシーを追加するには|追加するための手順について説明します、 **ProcessPurchaseOrder**ポリシーを**RuleTestApp**アプリケーション。|  
  
3.  3 番目のチュートリアルには展開手順が含まれています、 **ProcessPurchaseOrder** MSI ファイルを使用してポリシーが BizTalk Server 管理コンソールからエクスポートします。 次の表では、このチュートリアルの手順について説明します。  
  
    |プロシージャ タイトル|手順の詳細な手順では|  
    |---------------------|---------------------------------------------------|  
    |RuleTestApp アプリケーションを MSI ファイルをエクスポートするには|エクスポートするための手順について説明します、 **RuleTestApp**を MSI ファイルを後で、アプリケーションを再作成に使用されるアプリケーション。|  
    |RuleTestApp アプリケーションを削除するには|削除するための手順について説明します、 **RuleTestApp**アプリケーションの MSI ファイルを使用してアプリケーションを再作成をテストできるようにします。|  
    |ProcessPurchaseOrder ポリシーと POVocabulary ボキャブラリが削除されたことを確認するには|ビジネス ルール作成ツールを使用していることを確認する手順について説明します、 **ProcessPurchaseOrder**ポリシーと POVocabulary ボキャブラリが削除されます。|  
    |RuleTestApp アプリケーションを再作成する MSI ファイルをインポートするには|再作成する、BizTalk Server 管理コンソールを使用して MSI ファイルをインポートする手順について説明します、 **RuleTestApp**アプリケーション。|  
    |RuleTestApp に ProcessPurchaseOrder ポリシーが追加されたことを確認するには|BizTalk Server 管理コンソールを使用していることを確認する手順について説明します、 **ProcessPurchaseOrder**ポリシーに追加されます、 **RuleTestApp**アプリケーション。|  
    |ProcessPurchaseOrder ポリシーと POVocabulary ボキャブラリが再作成されたことを確認するには|ビジネス ルール作成ツールを使用していることを確認する手順について説明します、 **ProcessPurchaseOrder**ポリシーと**POVocabulary**ボキャブラリが再作成されます。|  
    |ソリューションをテストするには、次の操作を行います。|ソリューションをテストします。|  
  
## <a name="procedures-for-deploying-the-processpurchaseorder-policy-by-using-the-business-rules-engine-deployment-wizard"></a>ビジネス ルール エンジン展開ウィザードを使用して ProcessPurchaseOrder ポリシーを展開するための手順  
  
#### <a name="to-export-povocabulary-10-and-11-by-using-the-business-rules-engine-deployment-wizard"></a>ビジネス ルール エンジン展開ウィザードを使用して POVocabulary 1.0 および 1.1 をエクスポートするには  
  
1.  **開始**] メニューの [open**ビジネス ルール エンジン展開ウィザード**します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**します。  
  
2.  **[次へ]** をクリックします。  
  
3.  **展開タスク**] ページで、[**エクスポート ポリシー/ボキャブラリをファイルにデータベースから**、順にクリックします**次**します。  
  
4.  **ポリシー ストア**] ページで [**次**します。  
  
5.  **ポリシー/ボキャブラリのエクスポート**] ページで [**ボキャブラリ**します。  
  
6.  選択**POVocabulary.1.0**のドロップダウン リストから**ポリシー/ボキャブラリ**入力するか、XML 出力ファイル名を指定する参照**C:\BRE-walkthroughs\POVocabulary10.xml**、 をクリックし、**次**します。  
  
7.  **準備ができて**] ページで [**次**。  
  
8.  **ポリシー/ボキャブラリのエクスポート**] ページで [ **[次へ]。**  
  
9. 選択**このウィザードを再度実行**、 をクリックし、**完了**。  
  
     選択したので、**このウィザードを再度実行**ウィザードの最初の画面が再度表示されます。  
  
10. 手順 2. ~ 6. を繰り返します。  
  
11. 選択**POVocabulary.1.1**のドロップダウン リストから**ポリシー/ボキャブラリ**入力するか、XML 出力ファイル名を指定する参照**C:\BRE-walkthroughs\POVocabulary11.xml**、 をクリックし、**次**します。  
  
12. 手順 8. と 9. を繰り返します。  
  
13. **[完了]** をクリックします。  
  
    > [!NOTE]
    >  バージョン 1.0 と version 1.1 の両方をエクスポートする必要がある**POVocabulary**ため**ProcessPurchaseOrder** 1.3 の両方のバージョンによって異なります**POVocabulary**します。 **許可される項目の最大数**バージョン 1.1 のボキャブラリから定義を使用します。 **要求された数量**と**要求の状態**バージョン 1.0 からの定義が使用されます。  
  
#### <a name="to-export-processpurchaseorder-13-by-using-the-business-rule-engine-deployment-wizard"></a>ビジネス ルール エンジン展開ウィザードを使用して ProcessPurchaseOrder 1.3 をエクスポートするには  
  
1.  **開始**] メニューの [open**ビジネス ルール エンジン展開ウィザード**します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**します。  
  
2.  **、ルール エンジン展開ウィザードへようこそ**] ページで [**次**します。  
  
3.  選択**エクスポート ポリシー/ボキャブラリをファイルにデータベースから**、順にクリックします**次**します。  
  
4.  **ポリシー ストア**] ページで [**次**します。  
  
5.  いることを確認、**ポリシー**オプションを選択します。  
  
6.  選択**ProcessPurchaseOrder.1.3**のドロップダウン リストから**ポリシー/ボキャブラリ**します。  
  
7.  入力するかを指定する参照**C:\BRE-walkthroughs\ProcessPOPolicy13.xml**として、XML 出力ファイル名。  
  
8.  をクリックして**次**4 回、順にクリックします**完了**。  
  
#### <a name="to-delete-processpurchaseorder-and-povocabulary"></a>ProcessPurchaseOrder および POVocabulary を削除するには  
  
1.  **開始**] メニューの [open**ビジネス ルール作成ツール**します。 開く、f5 キーを押して、またはをクリックを既にのビジネス ルール作成ツールがあるかどうかは**再読み込み**上、**ファイル**メニューを更新します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**します。  
  
2.  ポリシー エクスプ ローラー ウィンドウで、**ポリシー**、展開**ProcessPurchaseOrder**を右クリックして**バージョン 1.0**、順にクリックします**削除**. 場合**削除**は右クリックし、無効になっています。**バージョン 1.0**、順にクリックします**Undeploy**します。  
  
    > [!NOTE]
    >  展開されたポリシー バージョンを削除できません。 ポリシーのバージョンを削除する前に、ポリシーの展開を解除する必要があります。  
  
3.  クリックして**はい**確認のメッセージ ボックスにします。  
  
4.  手順 2. および 3. 削除を**バージョン 1.1**します。  
  
5.  手順 2. および 3. 削除を**バージョン 1.2**します。  
  
6.  右クリック**Version 1.3 - Deployed**、 をクリックし、 **Undeploy**します。 場合、 **Undeploy**オプションが無効になっている、この手順を無視します。  
  
7.  ファクト エクスプ ローラー ウィンドウで、**ボキャブラリ**を右クリックして**POVocabulary**、 をクリックし、**削除**します。  
  
#### <a name="to-import-from-xml-to-re-create-povocabulary-10-and-11"></a>POVocabulary 1.0 および 1.1 を再作成する XML からインポートするには  
  
1.  **開始**] メニューの [open**ビジネス ルール エンジン展開ウィザード**します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**します。  
  
2.  **、ルール エンジン展開ウィザードへようこそ**、 をクリックして**次**します。  
  
3.  **展開タスク**] ページで、[**インポート ポリシー/ボキャブラリをファイルからデータベースに発行し、**、順にクリックします**次**。  
  
4.  **ポリシー ストア**] ページで [**次**します。  
  
5.  参照し、選択、 **POVocabulary10.xml**最初の手順で作成したファイル。  
  
6.  をクリックして**オープン**かダブルクリック**POVocabulary10.xml**。  
  
7.  クリックして**次**ビジネス ルール エンジン展開ウィザードでします。  
  
8.  **[次へ]** をクリックします。  
  
9. **[次へ]** をクリックします。  
  
10. 選択**このウィザードを再度実行**、 をクリックし、**完了**。  
  
11. 手順 2 ~ 9 をインポートする**POVocabulary11.xml**します。  
  
12. **[完了]** をクリックします。  
  
#### <a name="to-verify-that-povocabulary-10-and-11-are-re-created"></a>確認するには、その POVocabulary 1.0 および 1.1 が再作成されます。  
  
1.  **開始**] メニューの [open**ビジネス ルール作成ツール**します。 既に開かれていることがある場合、f5 キーを押すか をクリックして**再読み込み**上、**ファイル**メニューを更新します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**します。  
  
2.  [ファクト エクスプ ローラー] ウィンドウ、**ボキャブラリ**タブ。  
  
3.  展開**ボキャブラリ**、ください**POVocabulary**します。  
  
4.  展開**POVocabulary**、ください**バージョン 1.0**と**バージョン 1.1**します。  
  
#### <a name="to-import-from-xml-to-re-create-processpurchaseorder-13"></a>ProcessPurchaseOrder 1.3 を再作成する XML からインポートするには  
  
1.  **開始**] メニューの [open**ビジネス ルール エンジン展開ウィザード**します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**します。  
  
2.  **、ルール エンジン展開ウィザードへようこそ**、 をクリックして**次**します。  
  
3.  **展開タスク**] ページで、[**インポート ポリシー/ボキャブラリをファイルからデータベースをファイルからデータベースに発行し、**、順にクリックします**次**。  
  
4.  **ポリシー ストア**] ページで [**次**します。  
  
5.  参照し、選択、 **ProcessPOPolicy13.xml**このチュートリアルで先ほど作成したファイル。  
  
6.  をクリックして**オープン**かダブルクリック**ProcessPOPolicy13.xml**。  
  
7.  クリックして**次**ビジネス ルール エンジン展開ウィザードでします。  
  
8.  **[次へ]** をクリックします。  
  
9. **[次へ]** をクリックし、 **[完了]** をクリックします。  
  
#### <a name="to-verify-that-processpurchaseorder-13-is-re-created"></a>ProcessPurchaseOrder 1.3 が再作成されたことを確認するには  
  
1.  **開始**] メニューの [open**ビジネス ルール作成ツール**します。 既に開かれていることがある場合、f5 キーを押すか をクリックして**再読み込み**上、**ファイル**メニューを更新します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**します。  
  
2.  ポリシー エクスプ ローラー ウィンドウで、**ポリシー**ください**ProcessPurchaseOrder**します。  
  
3.  展開**ProcessPurchaseOrder**ください**Version 1.3 - Published**します。  
  
## <a name="procedures-for-deploying-the-policy-by-using-an-xml-file-exported-from-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールからエクスポートされたファイルの XML を使用して、ポリシーを展開するための手順  
  
#### <a name="to-export-the-processpurchaseorder-13-policy-and-the-povocabulary-vocabulary-to-an-xml-file"></a>ProcessPurchaseOrder 1.3 ポリシーと POVocabulary ボキャブラリを XML ファイルにエクスポートするには  
  
1. **開始**] メニューの [open[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]します。 既に開かれているツールがあれば、f5 キーを押して更新します。  
  
2. 展開**コンソール ルート**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**、順に展開**RuleTestApp**.  
  
3. クリックして**ポリシー**し、ProcessPurchaseOrder 1.3 ポリシーが一覧表示されるかどうかを確認します。  
  
4. 右クリックして**ProcessPurchaseOrder**、 をクリックし、**エクスポート**します。  
  
5. **ポリシーのエクスポート** ダイアログ ボックスで、確認、 **ProcessPurchaseOrder**ポリシーと**POVocabulary**が選択されています。  
  
   > [!NOTE]
   >  右クリックし、XML ファイルに、アプリケーション内のすべてのポリシーをエクスポートする**RuleTest**  をクリックし、**エクスポート**で、**ポリシー**メニュー。 このようにすべてのポリシーと単一の XML ファイルには、このアプリケーションで使用されるボキャブラリをエクスポートできます。  
  
   > [!NOTE]
   >  右クリックし、XML ファイルにすべてのアプリケーション内のすべてのポリシーをエクスポートすることができます、**アプリケーション**ノードをクリックして**エクスポート**上、**ポリシー**メニュー。 このように、すべてのポリシーと 1 つの XML ファイルにすべてのアプリケーションで使用されているボキャブラリをエクスポートできます。  
  
6. 出力 XML ファイル名を指定 (**C:\BRE-Walkthroughs\ProcessPOFromAdmin.xml**)、をクリックし、 **Ok**します。  
  
#### <a name="to-delete-the-processpurchaseorder-policy"></a>ProcessPurchaseOrder ポリシーを削除するには  
  
1.  BizTalk Server 管理コンソールで、右クリック**ProcessPurchaseOrder**  をクリックし、一覧で**削除**します。  
  
2.  をクリックして**はい**で、**削除ポリシー**メッセージ ボックス。  
  
    > [!NOTE]
    >  ポリシーが展開された状態にある場合は削除できません。 右クリック**ProcessPurchaseOrder**、順にクリックします**Undeploy**ポリシーの展開を解除します。 **削除**ポリシーが展開時に、メニュー項目が表示されます。  
  
    > [!NOTE]
    >  ボキャブラリ、 **ProcessPurchaseOrder**ここでポリシーが依存**POVocabulary**も削除されます。  
  
    > [!NOTE]
    >  アプリケーションからポリシーを削除するときに、ポリシーとボキャブラリに依存しているがアプリケーションからだけでなく同様に、ルール エンジン データベースから削除します。  
  
#### <a name="to-import-the-xml-file-to-re-create-the-processpurchaseorder-policy"></a>ProcessPurchaseOrder ポリシーを再作成する XML ファイルをインポートするには  
  
1. BizTalk Server 管理コンソールで **コンソール ルート**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、順に展開**BizTalk グループ**します。  
  
2. 右クリック**アプリケーション**、 をポイント**インポート**、 をクリックし、**ポリシー**します。  
  
3. 参照、および XML ファイルをダブルクリックします (**C:\BRE-Walkthroughs\ProcessPOFromAdmin.xml**)、最初の手順で作成しました。  
  
4. 展開**\<すべての成果物\>** **アプリケーション**します。  
  
5. クリックして**ポリシー**のバージョン 1.3 を確認する必要があります、 **ProcessPurchaseOrder**が一覧にします。  
  
6. F5 キーを押して表示を更新します。 **ProcessPurchaseOrder**にする必要があります、**非公開**状態。  
  
#### <a name="to-add-the-processpurchaseorder-policy-to-the-ruletestapp-application"></a>RuleTestApp アプリケーションに ProcessPurchaseOrder ポリシーを追加するには  
  
1.  BizTalk Server 管理コンソールで、右クリック**ProcessPurchaseOrder**ポリシー、およびクリック**発行**します。  
  
    > [!NOTE]
    >  公開済みのポリシーは、BizTalk アプリケーションに追加できます。  
  
2.  **アプリケーション**ノード展開**RuleTestApp**します。  
  
3.  クリックして**ポリシー**で**RuleTestApp**します。  
  
4.  右側の一覧内を右クリックし、[**追加**、] をクリックし、**ポリシー**します。  
  
5.  展開、 **ProcessPurchaseOrder**ノードを選択、チェック ボックスを**バージョン 1.3 (Published)**、順にクリックします**OK**します。 .  
  
6.  右クリック**ProcessPurchaseOrder**、 をクリックし、**デプロイ**します。 表示されない場合**ProcessPurchaseOrder**一覧で、f5 キーを押して表示を更新します。  
  
7.  クリックして**はい**確認のメッセージ ボックスにします。  
  
## <a name="procedures-for-deploying-the-policy-by-using-an-msi-file"></a>MSI ファイルを使用して、ポリシーを展開するための手順  
  
#### <a name="to-export-the-ruletestapp-application-to-an-msi-file"></a>RuleTestApp アプリケーションを MSI ファイルをエクスポートするには  
  
1. **開始**] メニューの [open **BizTalk Server 管理**します。 既に開かれているツールがあれば、f5 キーを押して更新します。  
  
2. 展開**コンソール ルート**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、順に展開**アプリケーション**します。  
  
3. 右クリックして**RuleTestApp**、 をポイント**エクスポート**、順にクリックします**MSI ファイル**します。  
  
4. **MSI ファイルのエクスポート ウィザードへようこそ**] ページで [**次**します。  
  
5. **リソースの選択**ページで既定のオプションすべてを確認し、をクリックし、**次**します。  
  
6. **IIS ホストの指定**] ページで [**次**します。  
  
7. **依存関係**] ページで [**次**します。  
  
8. **先**として MSI の名前とディレクトリの指定 ページで、 **C:\BRE-Walkthroughs\RuleTestApp.msi**します。  
  
9. **[エクスポート]** をクリックします。  
  
10. **概要**] ページで [**完了**します。  
  
    > [!NOTE]
    >  RuleTestApp アプリケーションをエクスポートするときに、ポリシーとボキャブラリを使って、アプリケーションは MSI ファイルにもエクスポートします。 後で、MSI ファイル、ボキャブラリ、ポリシー、およびアプリケーションをインポートすると、すべて再作成します。  
  
#### <a name="to-delete-the-ruletestapp-application"></a>RuleTestApp アプリケーションを削除するには  
  
1.  BizTalk Server 管理コンソールで、右クリック**RuleTestApp**、確認の場合と、**削除**メニューを有効または無効になっています。  
  
2.  場合**削除**は右クリックし、無効になっています**RuleTestApp**、 をクリック**停止**を選択します**完全停止 - インスタンスの終了**、順にクリックします。**停止**します。  
  
3.  右クリック**RuleTestApp**、 をクリックし、**削除**します。  
  
4.  クリックして**はい**削除を確定します。  
  
    > [!NOTE]
    >  アプリケーションを削除するときにすべてのポリシー、アプリケーションと依存するボキャブラリをルール エンジン データベースから削除されます。  
  
#### <a name="to-verify-that-the-processpurchaseorder-policy-and-povocabulary-vocabulary-are-deleted"></a>ProcessPurchaseOrder ポリシーと POVocabulary ボキャブラリが削除されたことを確認するには  
  
1.  **開始**] メニューの [open**ビジネス ルール作成ツール**します。 既にを開き、更新、f5 キーを押してのビジネス ルール作成ツールの場合は。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**します。  
  
2.  ポリシー エクスプ ローラー ウィンドウで、**ポリシー**、ProcessPurchaseOrder ポリシーが存在しないことを確認します。  
  
3.  ファクト エクスプ ローラー ウィンドウで、**ボキャブラリ**POVocabulary が存在しないことを確認します。  
  
#### <a name="to-import-the-msi-file-to-re-create-the-ruletestapp-application"></a>RuleTestApp アプリケーションを再作成する MSI ファイルをインポートするには  
  
1. **開始**] メニューの [open **BizTalk Server 管理**します。 BizTalk Server 管理コンソールを既に開いている場合は、F5 キーを押して更新します。  
  
2. 展開**コンソール ルート**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、順に展開**BizTalk グループ**します。  
  
3. 右クリック**アプリケーション**、 をポイント**インポート**、 をクリックし、 **MSI ファイル**します。  
  
4. **のインポート ウィザードへようこそ** ページで 参照 しての前にエクスポートした MSI ファイル (RuleTestApp.msi) を選択して、**インポートする MSI ファイル**設定。  
  
5. **[次へ]** をクリックします。  
  
6. **アプリケーション設定**] ページで [**次**します。  
  
7. **アプリケーション ターゲット環境の設定**] ページで [**次**します。  
  
8. **インポートの概要**] ページで [**インポート**します。  
  
9. **インポートに成功しました**] ページで [**完了**します。 表示する必要があります、 **RuleTestApp**下にアプリケーションが作成**アプリケーション**BizTalk Server 管理コンソールでします。  
  
#### <a name="to-verify-that-the-processpurchaseorder-policy-is-added-to-ruletestapp"></a>RuleTestApp に ProcessPurchaseOrder ポリシーが追加されたことを確認するには  
  
1.  展開**RuleTestApp** BizTalk Server 管理コンソールでします。  
  
2.  選択**ポリシー**と表示されます**ProcessPurchaseOrder**右側のウィンドウの一覧。  
  
#### <a name="to-verify-that-the-processpurchaseorder-policy-and-povocabulary-vocabulary-are-re-created"></a>ProcessPurchaseOrder ポリシーと POVocabulary ボキャブラリが再作成されたことを確認するには  
  
1.  **開始**] メニューの [open**ビジネス ルール作成ツール**します。 これがある場合、既に開かれている f5 キーを押して更新します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**します。  
  
2.  ポリシー エクスプ ローラー ウィンドウで、**ポリシー**、ことを確認および**ProcessPurchaseOrder**存在します。  
  
3.  ファクト エクスプ ローラー ウィンドウで、**ボキャブラリ**、ことを確認および**POVocabulary**存在します。  
  
#### <a name="to-test-the-solution"></a>ソリューションをテストするには、次の操作を行います。  
  
1. **開始**] メニューの [open **BizTalk Server 管理**します。 BizTalk Server 管理コンソールを既に開いている場合は、F5 キーを押して更新します。  
  
2. 展開**コンソール ルート**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、順に展開**アプリケーション**します。  
  
3. 右クリック**RuleTestApp**、 をクリックし、**開始**します。  
  
4. クリックして**開始**します。  
  
5. コピー **SamplePO.xml**で作成した[チュートリアル。ポリシーのテスト](../core/walkthrough-testing-the-policy.md)オーケストレーションの入力ディレクトリにします。  
  
6. オーケストレーションの出力ディレクトリに出力ファイルを確認する必要があります。 出力 XML ファイルを開き、注意の値、**状態**にフィールドが設定されている**Approved**します。  
  
7. 手順 3. と 4. を繰り返します**SamplePO2.xml**、いることを確認しの値、**状態**出力ドキュメント内のフィールドは、入力ドキュメントと同じ (**XYZ**)。  
  
## <a name="comments"></a>コメント  
  
-   **非常に重要な**ことに注意して、アプリケーションからポリシーを削除するときをだけを削除しないアプリケーションとポリシー間の関連付けは、するも、ポリシーとその関連付けられたボキャブラリをルールから削除エンジンのデータベースです。  
  
-   既定では、アプリケーションを起動するときに、ポリシーを自動的に配置します。 同様に、アプリケーションを停止し、選択する**完全停止 - インスタンスを終了**、関連付けられているポリシーは展開解除に自動的にします。 選択すると**部分停止 - 実行中のインスタンスを中断**、関連付けられているポリシーが解除されません自動的にします。  
  
-   ビジネス ルール作成ツールと BizTalk Server 管理コンソールのいずれかの操作を実行する前に最新の情報が表示されているかどうかを確認するビューを更新する必要があります。  
  
-   以前のバージョンが BizTalk アプリケーションに関連付けられたポリシーの新しいバージョンを作成する場合は、アプリケーションに新しいバージョンのポリシーを手動で追加する必要があります。 実際に、ルール エンジン データベースから削除する場合、古いバージョンのポリシーを削除しないでください。  
  
-   インポートする前に、単一の BRL ファイルに 2 つまたは複数の BRL (ビジネス ルール言語 XML ファイル) ファイルをマージできます。 次のコードでは、3 つの BRL ファイルを示します。 最初の BRL ファイルに含まれる、 **POVocabulary**ボキャブラリです。 2 番目の BRL ファイルに含まれる、 **ProcessPurchaseOrder**ポリシー。 3 番目の BRL ファイルには、両方が含まれています、 **POVocabulary**ボキャブラリと**ProcessPurchaseOrder**ポリシー。 3 番目の BRE ファイルは、次の手順を実行することによって作成されます。  
  
    1.  エディターの任意のファイルを使用して新しいファイルを作成し、XML ファイルとして保存します (例。POPolicyVocabulary.xml)。  
  
    2.  ボキャブラリを含む最初の BRL ファイルから XML コンテンツ全体をコピーします。  
  
    3.  ルール セット ブロックのコピー (で始まる、 \<ruleset\>タグと末尾には、 \</ruleset\>タグ)、2 番目の BRL ファイルから。  
  
    4.  新しいファイルを保存します。 この単一の XML ファイルを作成するをインポートすることができます、 **POVocabulary**ボキャブラリと**ProcessPurchaseOrder**ポリシー。  
  
    > [!NOTE]
    >  関係ありません順序ボキャブラリと ruleset ノードは、結合された BRL ファイルに表示されます。 ルール セット ノードをボキャブラリ ノードよりことができます。  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <brl  
    xmlns="http://schemas.microsoft.com/businessruleslanguage/2002">  
      <vocabulary id="e588676a-ba01-4f37-b59d-91f7e1eb1f1a" name="POVocabulary" uri="" description="">  
           ……   
      </vocabulary>  
    </brl>  
  
    <?xml version="1.0" encoding="utf-8"?>  
    <brl  
    xmlns="http://schemas.microsoft.com/businessruleslanguage/2002">  
      <ruleset name="ProcessPurchaseOrder">  
         ……  
      </ruleset>  
    </brl>  
  
    <brl  
    xmlns="http://schemas.microsoft.com/businessruleslanguage/2002">  
      <vocabulary id="e588676a-ba01-4f37-b59d-91f7e1eb1f1a" name="POVocabulary" uri="" description="">  
           ……   
      </vocabulary>  
      <ruleset name="ProcessPurchaseOrder">  
         ……  
      </ruleset>  
    </brl>  
    ```