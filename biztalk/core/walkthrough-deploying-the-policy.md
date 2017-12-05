---
title: "チュートリアル: ポリシーを展開する |Microsoft ドキュメント"
ms.custom: 
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 205760e2-9cd4-496f-93cd-0f93bc5d3231
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d235fa0f6882ecd9e180aabd26999b1d7f73390
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="walkthrough-deploying-the-policy"></a>チュートリアル: ポリシーを展開します。
このチュートリアルでを展開する手順、 **ProcessPurchaseOrder**次の 3 つの方法でポリシー。  
  
-   エクスポートして、ビジネス ルール エンジン展開ウィザードを使用して、ポリシーをインポートします。  
  
-   BizTalk Server 管理コンソールを使用して、XML ファイルにポリシーをエクスポートし、XML ファイルからポリシーをインポートする。  
  
-   BizTalk Server 管理コンソールを使用して、ポリシーを MSI ファイルの一部としてエクスポートし、MSI ファイルをインポートする。  
  
## <a name="prerequisites"></a>前提条件  
 完了する必要があります、[チュートリアル: ポリシーの実行を追跡](../core/walkthrough-tracking-policy-execution.md)このチュートリアルを実行する前にチュートリアルです。  
  
## <a name="overview-of-this-walkthrough"></a>このチュートリアルの概要  
 このトピックは次の 3 つのチュートリアルで構成されます。  
  
1.  最初のチュートリアルには展開手順が含まれています、 **ProcessPurchaseOrder**ビジネス ルール エンジン展開ウィザードを使用してポリシー。 次の表に、このチュートリアルの手順を示します。  
  
    |手順のタイトル|手順の説明|  
    |---------------------|---------------------------|  
    |ビジネス ルール エンジン展開ウィザードを使用して POVocabulary 1.0 および 1.1 をエクスポートするには|バージョン 1.0 および 1.1 をエクスポートするための手順をわかりやすく説明、 **POVocabulary**ボキャブラリを XML ファイルをビジネス ルール エンジン展開ウィザードを使用します。|  
    |ビジネス ルール エンジン展開ウィザードを使用して ProcessPurchaseOrder 1.3 をエクスポートするには|バージョン 1.3 をエクスポートするための手順をわかりやすく説明、 **ProcessPurchaseOrder**ポリシーをビジネス ルール エンジン展開ウィザードを使用して、XML ファイルです。|  
    |ProcessPurchaseOrder および POVocabulary を削除するには|削除するための手順をわかりやすく説明、 **ProcessPurchaseOrder**ポリシーおよび**POVocabulary**ボキャブラリがテストできるように XML ファイルのインポートを再作成します。|  
    |XML からインポートして POVocabulary 1.0 および 1.1 を再作成するには|再作成する最初の手順で作成したボキャブラリ XML ファイルをインポートするための手順をわかりやすく説明、 **POVocabulary**ボキャブラリです。|  
    |POVocabulary 1.0 および 1.1 が再作成されたことを確認するには|ビジネス ルール作成ツールを使用して、ことを確認するための手順をわかりやすく説明のバージョン 1.0 および 1.1 **POVocabulary**で再作成されます。|  
    |XML からインポートして ProcessPurchaseOrder 1.3 を再作成するには|バージョン 1.3 を再作成する 2 番目の手順で作成したポリシー XML ファイルをインポートするための手順をわかりやすく説明、 **ProcessPurchaseOrder**ポリシー。|  
    |ProcessPurchaseOrder 1.3 が再作成されたことを確認するには|ビジネス ルール作成ツールを使用してそのバージョン 1.3 のことを確認するための手順をわかりやすく説明、 **ProcessPurchaseOrder**ポリシーを再作成します。|  
  
2.  2 番目のチュートリアルには展開手順が含まれています、 **ProcessPurchaseOrder**次の BizTalk Server 管理コンソールからエクスポートしたポリシー XML ファイルを使用してテーブルには、この手順がについて説明しますチュートリアルです。  
  
    |手順のタイトル|手順の説明|  
    |---------------------|---------------------------|  
    |ProcessPurchaseOrder 1.3 ポリシーと POVocabulary ボキャブラリを XML ファイルにエクスポートするには|BizTalk Server 管理コンソールを使用して、エクスポートするための手順をわかりやすく説明、 **ProcessPurchaseOrder**ポリシーおよび**POVocabulary**ボキャブラリを XML ファイルにします。|  
    |ProcessPurchaseOrder ポリシーを削除するには|削除するための手順をわかりやすく説明、 **ProcessPurchaseOrder**からポリシーを**RuleTestApp**とルール エンジン データベース。|  
    |XML ファイルをインポートして ProcessPurchaseOrder ポリシーを再作成するには|再作成する最初の手順でエクスポートした XML ファイルをインポートするための手順をわかりやすく説明、 **ProcessPurchaseOrder**ポリシー。|  
    |RuleTestApp アプリケーションに ProcessPurchaseOrder ポリシーを追加するには|追加するための手順をわかりやすく説明、 **ProcessPurchaseOrder**ポリシーを**RuleTestApp**アプリケーションです。|  
  
3.  3 番目のチュートリアルには展開手順が含まれています、 **ProcessPurchaseOrder** MSI ファイルを使用してポリシーが BizTalk Server 管理コンソールからエクスポートします。 次の表に、このチュートリアルの手順を示します。  
  
    |手順のタイトル|手順に含まれるステップごとの説明|  
    |---------------------|---------------------------------------------------|  
    |RuleTestApp アプリケーションを MSI ファイルにエクスポートするには|エクスポートするための手順をわかりやすく説明、 **RuleTestApp**を MSI ファイルを後でアプリケーションを再作成に使用されるアプリケーション。|  
    |RuleTestApp アプリケーションを削除するには|削除するための手順をわかりやすく説明、 **RuleTestApp**アプリケーションの MSI ファイルを使用してアプリケーションを再作成がテストできるようにします。|  
    |ProcessPurchaseOrder ポリシーと POVocabulary ボキャブラリが削除されたことを確認するには|ビジネス ルール作成ツールを使用していることを確認するための手順をわかりやすく説明、 **ProcessPurchaseOrder**ポリシーと POVocabulary ボキャブラリが削除されます。|  
    |MSI ファイルをインポートして RuleTestApp アプリケーションを再作成するには|再作成する、BizTalk Server 管理コンソールを使用して MSI ファイルをインポートするための手順をわかりやすく説明、 **RuleTestApp**アプリケーションです。|  
    |RuleTestApp に ProcessPurchaseOrder ポリシーが追加されたことを確認するには|BizTalk Server 管理コンソールを使用していることを確認するための手順をわかりやすく説明、 **ProcessPurchaseOrder**ポリシーに追加、 **RuleTestApp**アプリケーションです。|  
    |ProcessPurchaseOrder ポリシーと POVocabulary ボキャブラリが再作成されたことを確認するには|ビジネス ルール作成ツールを使用していることを確認するための手順をわかりやすく説明、 **ProcessPurchaseOrder**ポリシーおよび**POVocabulary**ボキャブラリが再作成されます。|  
    |ソリューションをテストするには、次の操作を行います。|ソリューションをテストします。|  
  
## <a name="procedures-for-deploying-the-processpurchaseorder-policy-by-using-the-business-rules-engine-deployment-wizard"></a>ビジネス ルール エンジン展開ウィザードを使用して ProcessPurchaseOrder ポリシーを展開するための手順  
  
#### <a name="to-export-povocabulary-10-and-11-by-using-the-business-rules-engine-deployment-wizard"></a>ビジネス ルール エンジン展開ウィザードを使用して POVocabulary 1.0 および 1.1 をエクスポートするには  
  
1.  **開始**] メニューの [開いている**ビジネス ルール エンジン展開ウィザード**です。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**です。  
  
2.  **[次へ]**をクリックします。  
  
3.  **展開タスク**] ページで、[**エクスポート ポリシー/ボキャブラリをファイルにデータベースから**、順にクリック**次**です。  
  
4.  **ポリシー ストア**] ページで [**次**です。  
  
5.  **ポリシー/ボキャブラリのエクスポート**] ページで [**ボキャブラリ**です。  
  
6.  選択**POVocabulary.1.0**のドロップダウン リストから**ポリシー/ボキャブラリ**を入力するか、XML 出力ファイル名を指定する参照**C:\BRE-walkthroughs\POVocabulary10.xml**、クリックして**次**です。  
  
7.  **準備** ページで、をクリックして**次**です。  
  
8.  **ポリシー/ボキャブラリのエクスポート**] ページで [ **[次へ] です。**  
  
9. 選択**このウィザードを再度実行**、順にクリック**完了**です。  
  
     選択したので、**このウィザードを再度実行**ウィザードの最初の画面が再度表示されます。  
  
10. 手順 2. ~ 6. を繰り返します。  
  
11. 選択**POVocabulary.1.1**のドロップダウン リストから**ポリシー/ボキャブラリ**を入力するか、XML 出力ファイル名を指定する参照**C:\BRE-walkthroughs\POVocabulary11.xml**、クリックして**次**です。  
  
12. 手順 8. ～ 9. を繰り返します。  
  
13. **[完了]**をクリックします。  
  
    > [!NOTE]
    >  バージョン 1.0 および 1.1 の両方をエクスポートする必要が**POVocabulary**ため**ProcessPurchaseOrder** 1.3 の両方のバージョンによって異なります**POVocabulary**です。 **許可される項目の最大数**バージョン 1.1 のボキャブラリから定義を使用します。 **要求された数量**と**要求の状態**定義はバージョン 1.0 から使用されます。  
  
#### <a name="to-export-processpurchaseorder-13-by-using-the-business-rule-engine-deployment-wizard"></a>ビジネス ルール エンジン展開ウィザードを使用して ProcessPurchaseOrder 1.3 をエクスポートするには  
  
1.  **開始**] メニューの [開いている**ビジネス ルール エンジン展開ウィザード**です。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**です。  
  
2.  **ルール エンジン展開ウィザードへようこそ** ページで、をクリックして**次**です。  
  
3.  選択**エクスポート ポリシー/ボキャブラリをファイルにデータベースから**、順にクリック**次**です。  
  
4.  **ポリシー ストア**] ページで [**次**です。  
  
5.  いることを確認、**ポリシー**オプションを選択します。  
  
6.  選択**ProcessPurchaseOrder.1.3**のドロップダウン リストから**ポリシー/ボキャブラリ**です。  
  
7.  入力するかを指定する参照**C:\BRE-walkthroughs\ProcessPOPolicy13.xml** XML 出力ファイル名として。  
  
8.  をクリックして**[次へ]** 4 回、順にクリック**完了**です。  
  
#### <a name="to-delete-processpurchaseorder-and-povocabulary"></a>ProcessPurchaseOrder および POVocabulary を削除するには  
  
1.  **開始**] メニューの [開いている**ビジネス ルール作成ツール**です。 開く、f5 キーを押して、またはをクリックを既にのビジネス ルール作成ツールがあるかどうか**再読み込み**で、**ファイル**メニューを更新します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**です。  
  
2.  ポリシー エクスプ ローラー ウィンドウで、**ポリシー**、展開**ProcessPurchaseOrder**を右クリックして**バージョン 1.0**、クリックして**を削除**. 場合**削除**は無効になっているを右クリックし**バージョン 1.0**をクリックし、 **Undeploy**です。  
  
    > [!NOTE]
    >  展開されたポリシー バージョンは削除できません。 ポリシー バージョンを削除する前に、ポリシーを展開解除する必要があります。  
  
3.  をクリックして**はい**確認のメッセージ ボックスにします。  
  
4.  手順 2 および 3 を削除する**バージョン 1.1**です。  
  
5.  手順 2 および 3 を削除する**バージョン 1.2**です。  
  
6.  右クリック**Version 1.3 - Deployed**、クリックして**Undeploy**です。 場合、 **Undeploy**オプションが無効になっている、この手順を無視します。  
  
7.  ファクト エクスプ ローラー ウィンドウで、**ボキャブラリ**を右クリックして**POVocabulary**、クリックして**削除**です。  
  
#### <a name="to-import-from-xml-to-re-create-povocabulary-10-and-11"></a>XML からインポートして POVocabulary 1.0 および 1.1 を再作成するには  
  
1.  **開始**] メニューの [開いている**ビジネス ルール エンジン展開ウィザード**です。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**です。  
  
2.  **ルール エンジン展開ウィザードへようこそ**、 をクリックして**次**です。  
  
3.  **展開タスク**] ページで、[**インポート ポリシー/ボキャブラリをファイルからデータベースに発行し、**、順にクリック**次**です。  
  
4.  **ポリシー ストア**] ページで [**次**です。  
  
5.  参照し、選択、 **POVocabulary10.xml**最初の手順で作成したファイルです。  
  
6.  をクリックして**開く**ダブルクリックまたは**POVocabulary10.xml**です。  
  
7.  をクリックして**次**ビジネス ルール エンジン展開ウィザードでします。  
  
8.  **[次へ]**をクリックします。  
  
9. **[次へ]**をクリックします。  
  
10. 選択**このウィザードを再度実行**、順にクリック**完了**です。  
  
11. 手順 2 ~ 9 をインポートする**POVocabulary11.xml**です。  
  
12. **[完了]**をクリックします。  
  
#### <a name="to-verify-that-povocabulary-10-and-11-are-re-created"></a>POVocabulary 1.0 および 1.1 が再作成されたことを確認するには  
  
1.  **開始**] メニューの [開いている**ビジネス ルール作成ツール**です。 既に開かれていることがある場合、f5 キーを押すか をクリックして**再読み込み**上、**ファイル**メニューを更新します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**です。  
  
2.  [ファクト エクスプ ローラー] ウィンドウ、**ボキャブラリ**タブです。  
  
3.  展開**ボキャブラリ**、ください**POVocabulary**です。  
  
4.  展開**POVocabulary**、ください**バージョン 1.0**と**バージョン 1.1**です。  
  
#### <a name="to-import-from-xml-to-re-create-processpurchaseorder-13"></a>XML からインポートして ProcessPurchaseOrder 1.3 を再作成するには  
  
1.  **開始**] メニューの [開いている**ビジネス ルール エンジン展開ウィザード**です。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**です。  
  
2.  **ルール エンジン展開ウィザードへようこそ**、 をクリックして**次**です。  
  
3.  **展開タスク**] ページで、[**インポート ポリシー/ボキャブラリをファイルからデータベースをファイルからデータベースに発行し、**、順にクリック**次**です。  
  
4.  **ポリシー ストア**] ページで [**次**です。  
  
5.  参照し、選択、 **ProcessPOPolicy13.xml**このチュートリアルで先ほど作成したファイルです。  
  
6.  をクリックして**開く**ダブルクリックまたは**ProcessPOPolicy13.xml**です。  
  
7.  をクリックして**次**ビジネス ルール エンジン展開ウィザードでします。  
  
8.  **[次へ]**をクリックします。  
  
9. **[次へ]**をクリックし、 **[完了]**をクリックします。  
  
#### <a name="to-verify-that-processpurchaseorder-13-is-re-created"></a>ProcessPurchaseOrder 1.3 が再作成されたことを確認するには  
  
1.  **開始**] メニューの [開いている**ビジネス ルール作成ツール**です。 既に開かれていることがある場合、f5 キーを押すか をクリックして**再読み込み**上、**ファイル**メニューを更新します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**です。  
  
2.  ポリシー エクスプ ローラー ウィンドウで、**ポリシー**ください**ProcessPurchaseOrder**です。  
  
3.  展開**ProcessPurchaseOrder**ください**Version 1.3 - Published**です。  
  
## <a name="procedures-for-deploying-the-policy-by-using-an-xml-file-exported-from-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールからエクスポートした XML ファイルを使用したポリシーの展開手順  
  
#### <a name="to-export-the-processpurchaseorder-13-policy-and-the-povocabulary-vocabulary-to-an-xml-file"></a>ProcessPurchaseOrder 1.3 ポリシーと POVocabulary ボキャブラリを XML ファイルにエクスポートするには  
  
1.  **開始**] メニューの [開いている[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]です。 このツールを既に開いている場合は、F5 キーを押して更新します。  
  
2.  展開**コンソール ルート**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**、順に展開**RuleTestApp**.  
  
3.  をクリックして**ポリシー**し、ProcessPurchaseOrder 1.3 ポリシー一覧に表示されるかどうかを確認します。  
  
4.  右クリック**ProcessPurchaseOrder**、クリックして**エクスポート**です。  
  
5.  **ポリシーのエクスポート** ダイアログ ボックスで、確認、 **ProcessPurchaseOrder**ポリシーおよび**POVocabulary**が選択されています。  
  
    > [!NOTE]
    >  右クリックして、アプリケーションを XML ファイル内のすべてのポリシーをエクスポートすることができます**RuleTest**クリックし、**エクスポート**上、**ポリシー**メニュー。 この方法により、このアプリケーションで使用されるすべてのポリシーとボキャブラリを、単一の XML ファイルにエクスポートできます。  
  
    > [!NOTE]
    >  右クリックして XML ファイルへのすべてのアプリケーション内のすべてのポリシーをエクスポートすることができます、**アプリケーション**ノードをクリックして**エクスポート**上、**ポリシー**メニュー。 この方法により、すべてのアプリケーションで使用されるすべてのポリシーとボキャブラリを、単一の XML ファイルにエクスポートできます。  
  
6.  出力 XML ファイル名を指定 (**C:\BRE-Walkthroughs\ProcessPOFromAdmin.xml**)、をクリックして**Ok**です。  
  
#### <a name="to-delete-the-processpurchaseorder-policy"></a>ProcessPurchaseOrder ポリシーを削除するには  
  
1.  BizTalk Server 管理コンソールで、右クリック**ProcessPurchaseOrder**  をクリックし、一覧で**削除**です。  
  
2.  をクリックして**はい**で、**を削除するポリシー**メッセージ ボックスです。  
  
    > [!NOTE]
    >  展開された状態のポリシーは削除できません。 右クリック**ProcessPurchaseOrder**、順にクリック**Undeploy**ポリシーの展開を解除します。 **削除**ポリシーは展開されていない場合は、メニュー項目が表示されます。  
  
    > [!NOTE]
    >  ボキャブラリ、 **ProcessPurchaseOrder**ここでポリシーが依存**POVocabulary**も削除されます。  
  
    > [!NOTE]
    >  アプリケーションからポリシーを削除すると、そのポリシーと依存対象のボキャブラリは、アプリケーションからだけでなくルール エンジン データベースからも削除されます。  
  
#### <a name="to-import-the-xml-file-to-re-create-the-processpurchaseorder-policy"></a>XML ファイルをインポートして ProcessPurchaseOrder ポリシーを再作成するには  
  
1.  BizTalk Server 管理コンソールで、展開**コンソール ルート**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、順に展開**BizTalk グループ**です。  
  
2.  右クリック**アプリケーション**、 をポイント**インポート**、クリックして**ポリシー**です。  
  
3.  参照、および XML ファイルをダブルクリックして (**C:\BRE-Walkthroughs\ProcessPOFromAdmin.xml**) の最初の手順で作成しました。  
  
4.  展開**\<すべての成果物\>** **アプリケーション**です。  
  
5.  をクリックして**ポリシー**のバージョン 1.3 を表示する必要があります、 **ProcessPurchaseOrder**が一覧にします。  
  
6.  F5 キーを押してビューを更新します。 **ProcessPurchaseOrder**にポリシーがあります、**非公開**状態です。  
  
#### <a name="to-add-the-processpurchaseorder-policy-to-the-ruletestapp-application"></a>RuleTestApp アプリケーションに ProcessPurchaseOrder ポリシーを追加するには  
  
1.  BizTalk Server 管理コンソールで、右クリック**ProcessPurchaseOrder**ポリシー、およびクリック**発行**です。  
  
    > [!NOTE]
    >  BizTalk アプリケーションに追加できるのは、公開済みのポリシーだけです。  
  
2.  **アプリケーション** ノードを展開**RuleTestApp**です。  
  
3.  をクリックして**ポリシー**で**RuleTestApp**です。  
  
4.  右側の一覧内を右クリックし、**追加**、クリックして**ポリシー**です。  
  
5.  展開、 **ProcessPurchaseOrder**ノードで、チェック ボックスを選択**Version 1.3 (Published)**、クリックして**[ok]**です。 のインスタンスにアクセスするたびに SQL Server ログインを指定する必要はありません。  
  
6.  右クリック**ProcessPurchaseOrder**、クリックして**展開**です。 表示されない場合**ProcessPurchaseOrder**一覧で、f5 キーを押して表示を更新します。  
  
7.  をクリックして**はい**確認のメッセージ ボックスにします。  
  
## <a name="procedures-for-deploying-the-policy-by-using-an-msi-file"></a>MSI ファイルを使用したポリシーの展開手順  
  
#### <a name="to-export-the-ruletestapp-application-to-an-msi-file"></a>RuleTestApp アプリケーションを MSI ファイルにエクスポートするには  
  
1.  **開始**] メニューの [開いている**BizTalk Server 管理コンソール**です。 このツールを既に開いている場合は、F5 キーを押して更新します。  
  
2.  展開**コンソール ルート**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、順に展開**アプリケーション**です。  
  
3.  右クリック**RuleTestApp**、 をポイント**エクスポート**、クリックして**MSI ファイル**です。  
  
4.  **MSI ファイルのエクスポート ウィザードへようこそ** ページで、をクリックして**次**です。  
  
5.  **リソースの選択** ページで、すべての既定オプションを確認してをクリックして**次**です。  
  
6.  **IIS ホストの指定**] ページで [**次**です。  
  
7.  **の依存関係** ページで、をクリックして**次**です。  
  
8.  **先**として msi ファイルの名前とディレクトリを指定 ページで、 **C:\BRE-Walkthroughs\RuleTestApp.msi**です。  
  
9. **[エクスポート]**をクリックします。  
  
10. **概要**] ページで [**完了**です。  
  
    > [!NOTE]
    >  RuleTestApp アプリケーションをエクスポートすると、アプリケーションで使用されるポリシーとボキャブラリも MSI ファイルにエクスポートされます。 後で MSI ファイルをインポートすると、ボキャブラリ、ポリシー、およびアプリケーションが、すべて再作成されます。  
  
#### <a name="to-delete-the-ruletestapp-application"></a>RuleTestApp アプリケーションを削除するには  
  
1.  BizTalk Server 管理コンソールで、右クリック**RuleTestApp**、かどうか確認し、**削除**メニューを有効または無効にします。  
  
2.  場合**削除**は無効になっているを右クリックし**[ruletestapp]**、] をクリックして**停止**[**完全停止 - インスタンスの終了**をクリックして**停止**です。  
  
3.  右クリック**RuleTestApp**、クリックして**削除**です。  
  
4.  をクリックして**はい**削除を確認します。  
  
    > [!NOTE]
    >  アプリケーションを削除すると、アプリケーション内のすべてのポリシーとそれらが依存するボキャブラリも、ルール エンジン データベースから削除されます。  
  
#### <a name="to-verify-that-the-processpurchaseorder-policy-and-povocabulary-vocabulary-are-deleted"></a>ProcessPurchaseOrder ポリシーと POVocabulary ボキャブラリが削除されたことを確認するには  
  
1.  **開始**] メニューの [開いている**ビジネス ルール作成ツール**です。 ある場合は既にを開き、f5 キーを押して更新のビジネス ルール作成ツール。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**です。  
  
2.  ポリシー エクスプ ローラー ウィンドウで、**ポリシー**、ProcessPurchaseOrder ポリシーが存在しないことを確認します。  
  
3.  ファクト エクスプ ローラー ウィンドウで、**ボキャブラリ**POVocabulary が存在しないことを確認します。  
  
#### <a name="to-import-the-msi-file-to-re-create-the-ruletestapp-application"></a>MSI ファイルをインポートして RuleTestApp アプリケーションを再作成するには  
  
1.  **開始**] メニューの [開いている**BizTalk Server 管理コンソール**です。 BizTalk Server 管理コンソールを既に開いている場合は、F5 キーを押して更新します。  
  
2.  展開**コンソール ルート**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、順に展開**BizTalk グループ**です。  
  
3.  右クリック**アプリケーション**、 をポイント**インポート**、クリックして**MSI ファイル**です。  
  
4.  **のインポート ウィザードへようこそ**ページで、参照の前にエクスポートした MSI ファイル (RuleTestApp.msi) を選択し、**インポートする MSI ファイル**設定します。  
  
5.  **[次へ]**をクリックします。  
  
6.  **アプリケーション設定** ページで、をクリックして**次**です。  
  
7.  **アプリケーションのターゲット環境設定** ページで、をクリックして**次**です。  
  
8.  **インポートの概要**] ページで [**インポート**です。  
  
9. **インポートに成功しました**] ページで [**完了**です。 表示する必要があります、 **RuleTestApp**下にアプリケーションが作成**アプリケーション**BizTalk Server 管理コンソールでします。  
  
#### <a name="to-verify-that-the-processpurchaseorder-policy-is-added-to-ruletestapp"></a>RuleTestApp に ProcessPurchaseOrder ポリシーが追加されたことを確認するには  
  
1.  展開**RuleTestApp** BizTalk Server 管理コンソールでします。  
  
2.  選択**ポリシー**して表示**ProcessPurchaseOrder**右側のペインの一覧にします。  
  
#### <a name="to-verify-that-the-processpurchaseorder-policy-and-povocabulary-vocabulary-are-re-created"></a>ProcessPurchaseOrder ポリシーと POVocabulary ボキャブラリが再作成されたことを確認するには  
  
1.  **開始**] メニューの [開いている**ビジネス ルール作成ツール**です。 既に開いている場合は、F5 キーを押して更新します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**です。  
  
2.  ポリシー エクスプ ローラー ウィンドウで、**ポリシー**、ことを確認および**ProcessPurchaseOrder**が存在します。  
  
3.  ファクト エクスプ ローラー ウィンドウで、**ボキャブラリ**、ことを確認および**POVocabulary**が存在します。  
  
#### <a name="to-test-the-solution"></a>ソリューションをテストするには、次の操作を行います。  
  
1.  **開始**] メニューの [開いている**BizTalk Server 管理コンソール**です。 BizTalk Server 管理コンソールを既に開いている場合は、F5 キーを押して更新します。  
  
2.  展開**コンソール ルート**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、順に展開**アプリケーション**です。  
  
3.  右クリック**RuleTestApp**、クリックして**開始**です。  
  
4.  をクリックして**開始**です。  
  
5.  コピー **SamplePO.xml**で作成した[チュートリアル: ポリシーのテスト](../core/walkthrough-testing-the-policy.md)オーケストレーションの入力ディレクトリにします。  
  
6.  オーケストレーションの出力ディレクトリに、出力ファイルが表示されます。 出力 XML ファイルを開くことを確認の値、**ステータス**にフィールドが設定されている**Approved**です。  
  
7.  手順 3. と 4. を繰り返します**SamplePO2.xml**、ことを確認の値、**ステータス**出力ドキュメント内のフィールドは、入力ドキュメントと同じ (**XYZ**)。  
  
## <a name="comments"></a>コメント  
  
-   **非常に重要な**ことに注意して、アプリケーションからポリシーを削除するときをだけを削除しないと、アプリケーションとポリシーの関連付けです削除することも、ポリシーと関連付けられている語彙規則から。エンジンのデータベースです。  
  
-   既定では、アプリケーションを開始すると、ポリシーが自動的に展開されます。 同様に、アプリケーションを停止し、選択する**完全停止 - インスタンスを終了**、関連付けられているポリシーは展開解除自動的にします。 選択すると**部分停止 - 実行中のインスタンスを中断**、関連付けられているポリシーが解除されません自動的にします。  
  
-   ビジネス ルール作成ツールと BizTalk Server 管理コンソールで操作を実行する前には、ビューを更新して、最新の情報を確実に表示してください。  
  
-   以前のバージョンが BizTalk アプリケーションに関連付けられているポリシーに、新しいバージョンを作成する場合、ポリシーの新しいバージョンを手動でアプリケーションに追加してください。 ルール エンジン データベースから削除する場合を除いて、ポリシーの古いバージョンは削除しないでください。  
  
-   インポート前に、複数の BRL (ビジネス ルール言語 XML ファイル) ファイルを単一の BRL ファイルに結合できます。 次のコードは 3 つの BRL ファイルを示しています。 1 番目の BRL ファイルに含まれています、 **POVocabulary**ボキャブラリです。 2 番目の BRL ファイルに含まれる、 **ProcessPurchaseOrder**ポリシー。 3 番目の BRL ファイルには、両方が含まれています、 **POVocabulary**ボキャブラリと**ProcessPurchaseOrder**ポリシー。 3 番目の BRE ファイルを作成するには、次の手順を実行します。  
  
    1.  任意のファイルを使用して新しいファイル エディターを作成し、XML ファイルとして保存します (例: POPolicyVocabulary.xml)。  
  
    2.  ボキャブラリが含まれている 1 番目の BRL ファイルから、XML コンテンツ全体をコピーします。  
  
    3.  ルール セット ブロックのコピー (で始まる、 \<ruleset\>タグと末尾には、 \</ruleset\>タグ)、2 番目の BRL ファイルからです。  
  
    4.  新しいファイルを保存します。 この単一の XML ファイルを作成するをインポートすることができます、 **POVocabulary**ボキャブラリと**ProcessPurchaseOrder**ポリシー。  
  
    > [!NOTE]
    >  結合された BRL ファイル内での、ボキャブラリ ノードとルール セット ノードの順序に意味はありません。 ルール セット ノードをボキャブラリ ノードより前に置いてもかまいません。  
  
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