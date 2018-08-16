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
ms.openlocfilehash: b35b7d9c3b2b7780ef87b0dedae52f58c20dc835
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996299"
---
# <a name="walkthrough-deploying-the-policy"></a>チュートリアル: ポリシーの展開
このチュートリアルを展開するための手順について説明します、 **ProcessPurchaseOrder**次の 3 つの方法でポリシー。  
  
-   エクスポートして、ビジネス ルール エンジン展開ウィザードを使用して、ポリシーをインポートします。  
  
-   BizTalk Server 管理コンソールを使用して、XML ファイルにポリシーをエクスポートし、XML ファイルからポリシーをインポートする。  
  
-   BizTalk Server 管理コンソールを使用して、ポリシーを MSI ファイルの一部としてエクスポートし、MSI ファイルをインポートする。  
  
## <a name="prerequisites"></a>前提条件  
 完了する必要があります、[チュートリアル: ポリシーの実行を追跡](../core/walkthrough-tracking-policy-execution.md)このチュートリアルを実行する前にチュートリアル。  
  
## <a name="overview-of-this-walkthrough"></a>このチュートリアルの概要  
 このトピックは次の 3 つのチュートリアルで構成されます。  
  
1.  最初のチュートリアルには展開手順が含まれています、 **ProcessPurchaseOrder**ビジネス ルール エンジン展開ウィザードを使用してポリシー。 次の表に、このチュートリアルの手順を示します。  
  
    |プロシージャ タイトル|手順の説明|  
    |---------------------|---------------------------|  
    |ビジネス ルール エンジン展開ウィザードを使用して POVocabulary 1.0 および 1.1 をエクスポートするには|バージョン 1.0 および 1.1 をエクスポートするための手順について説明します、 **POVocabulary**ボキャブラリを XML には、ビジネス ルール エンジン展開ウィザードを使用してファイルします。|  
    |ビジネス ルール エンジン展開ウィザードを使用して ProcessPurchaseOrder 1.3 をエクスポートするには|バージョン 1.3 をエクスポートするための手順について説明します、 **ProcessPurchaseOrder**ビジネス ルール エンジン展開ウィザードを使用して XML ファイルにポリシー。|  
    |ProcessPurchaseOrder および POVocabulary を削除するには|削除するための手順について説明します、 **ProcessPurchaseOrder**ポリシーと**POVocabulary**ボキャブラリを再作成するファイル、XML のインポートをテストできるようにします。|  
    |XML からインポートして POVocabulary 1.0 および 1.1 を再作成するには|再作成する最初の手順で作成したボキャブラリ XML ファイルをインポートするための手順を提供します、 **POVocabulary**ボキャブラリです。|  
    |POVocabulary 1.0 および 1.1 が再作成されたことを確認するには|ビジネス ルール作成ツールを使用して検証するための手順は、のバージョン 1.0 および 1.1 **POVocabulary**は再作成します。|  
    |XML からインポートして ProcessPurchaseOrder 1.3 を再作成するには|バージョン 1.3 を再作成する 2 番目の手順で作成したポリシー XML ファイルをインポートするための手順を提供します、 **ProcessPurchaseOrder**ポリシー。|  
    |ProcessPurchaseOrder 1.3 が再作成されたことを確認するには|ビジネス ルール作成ツールを使用して、バージョン 1.3 を検証するための手順について説明します、 **ProcessPurchaseOrder**ポリシーが再作成されます。|  
  
2.  2 番目のチュートリアルには展開手順が含まれています、 **ProcessPurchaseOrder**次の BizTalk Server 管理コンソールからエクスポートされたポリシー XML ファイルを使用してテーブルには、この手順がについて説明しますチュートリアルです。  
  
    |プロシージャ タイトル|手順の説明|  
    |---------------------|---------------------------|  
    |ProcessPurchaseOrder 1.3 ポリシーと POVocabulary ボキャブラリを XML ファイルにエクスポートするには|BizTalk Server 管理コンソールを使用してエクスポートする手順について説明します、 **ProcessPurchaseOrder**ポリシーと**POVocabulary**ボキャブラリを XML ファイルにします。|  
    |ProcessPurchaseOrder ポリシーを削除するには|削除するための手順について説明します、 **ProcessPurchaseOrder**からポリシー **RuleTestApp**とルール エンジン データベース。|  
    |XML ファイルをインポートして ProcessPurchaseOrder ポリシーを再作成するには|再作成する最初の手順でエクスポートした XML ファイルをインポートするための手順を提供します、 **ProcessPurchaseOrder**ポリシー。|  
    |RuleTestApp アプリケーションに ProcessPurchaseOrder ポリシーを追加するには|追加するための手順について説明します、 **ProcessPurchaseOrder**ポリシーを**RuleTestApp**アプリケーション。|  
  
3.  3 番目のチュートリアルには展開手順が含まれています、 **ProcessPurchaseOrder** MSI ファイルを使用してポリシーが BizTalk Server 管理コンソールからエクスポートします。 次の表に、このチュートリアルの手順を示します。  
  
    |プロシージャ タイトル|手順に含まれるステップごとの説明|  
    |---------------------|---------------------------------------------------|  
    |RuleTestApp アプリケーションを MSI ファイルにエクスポートするには|エクスポートするための手順について説明します、 **RuleTestApp**を MSI ファイルを後で、アプリケーションを再作成に使用されるアプリケーション。|  
    |RuleTestApp アプリケーションを削除するには|削除するための手順について説明します、 **RuleTestApp**アプリケーションの MSI ファイルを使用してアプリケーションを再作成をテストできるようにします。|  
    |ProcessPurchaseOrder ポリシーと POVocabulary ボキャブラリが削除されたことを確認するには|ビジネス ルール作成ツールを使用していることを確認する手順について説明します、 **ProcessPurchaseOrder**ポリシーと POVocabulary ボキャブラリが削除されます。|  
    |MSI ファイルをインポートして RuleTestApp アプリケーションを再作成するには|再作成する、BizTalk Server 管理コンソールを使用して MSI ファイルをインポートする手順について説明します、 **RuleTestApp**アプリケーション。|  
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
  
12. 手順 8. ～ 9. を繰り返します。  
  
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
    >  展開されたポリシー バージョンは削除できません。 ポリシー バージョンを削除する前に、ポリシーを展開解除する必要があります。  
  
3.  クリックして**はい**確認のメッセージ ボックスにします。  
  
4.  手順 2. および 3. 削除を**バージョン 1.1**します。  
  
5.  手順 2. および 3. 削除を**バージョン 1.2**します。  
  
6.  右クリック**Version 1.3 - Deployed**、 をクリックし、 **Undeploy**します。 場合、 **Undeploy**オプションが無効になっている、この手順を無視します。  
  
7.  ファクト エクスプ ローラー ウィンドウで、**ボキャブラリ**を右クリックして**POVocabulary**、 をクリックし、**削除**します。  
  
#### <a name="to-import-from-xml-to-re-create-povocabulary-10-and-11"></a>XML からインポートして POVocabulary 1.0 および 1.1 を再作成するには  
  
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
  
#### <a name="to-verify-that-povocabulary-10-and-11-are-re-created"></a>POVocabulary 1.0 および 1.1 が再作成されたことを確認するには  
  
1.  **開始**] メニューの [open**ビジネス ルール作成ツール**します。 既に開かれていることがある場合、f5 キーを押すか をクリックして**再読み込み**上、**ファイル**メニューを更新します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**します。  
  
2.  [ファクト エクスプ ローラー] ウィンドウ、**ボキャブラリ**タブ。  
  
3.  展開**ボキャブラリ**、ください**POVocabulary**します。  
  
4.  展開**POVocabulary**、ください**バージョン 1.0**と**バージョン 1.1**します。  
  
#### <a name="to-import-from-xml-to-re-create-processpurchaseorder-13"></a>XML からインポートして ProcessPurchaseOrder 1.3 を再作成するには  
  
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
  
## <a name="procedures-for-deploying-the-policy-by-using-an-xml-file-exported-from-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールからエクスポートした XML ファイルを使用したポリシーの展開手順  
  
#### <a name="to-export-the-processpurchaseorder-13-policy-and-the-povocabulary-vocabulary-to-an-xml-file"></a>ProcessPurchaseOrder 1.3 ポリシーと POVocabulary ボキャブラリを XML ファイルにエクスポートするには  
  
1. **開始**] メニューの [open[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]します。 このツールを既に開いている場合は、F5 キーを押して更新します。  
  
2. 展開**コンソール ルート**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**、順に展開**RuleTestApp**.  
  
3. クリックして**ポリシー**し、ProcessPurchaseOrder 1.3 ポリシーが一覧表示されるかどうかを確認します。  
  
4. 右クリックして**ProcessPurchaseOrder**、 をクリックし、**エクスポート**します。  
  
5. **ポリシーのエクスポート** ダイアログ ボックスで、確認、 **ProcessPurchaseOrder**ポリシーと**POVocabulary**が選択されています。  
  
   > [!NOTE]
   >  右クリックし、XML ファイルに、アプリケーション内のすべてのポリシーをエクスポートする**RuleTest**  をクリックし、**エクスポート**で、**ポリシー**メニュー。 この方法により、このアプリケーションで使用されるすべてのポリシーとボキャブラリを、単一の XML ファイルにエクスポートできます。  
  
   > [!NOTE]
   >  右クリックし、XML ファイルにすべてのアプリケーション内のすべてのポリシーをエクスポートすることができます、**アプリケーション**ノードをクリックして**エクスポート**上、**ポリシー**メニュー。 この方法により、すべてのアプリケーションで使用されるすべてのポリシーとボキャブラリを、単一の XML ファイルにエクスポートできます。  
  
6. 出力 XML ファイル名を指定 (**C:\BRE-Walkthroughs\ProcessPOFromAdmin.xml**)、をクリックし、 **Ok**します。  
  
#### <a name="to-delete-the-processpurchaseorder-policy"></a>ProcessPurchaseOrder ポリシーを削除するには  
  
1.  BizTalk Server 管理コンソールで、右クリック**ProcessPurchaseOrder**  をクリックし、一覧で**削除**します。  
  
2.  をクリックして**はい**で、**削除ポリシー**メッセージ ボックス。  
  
    > [!NOTE]
    >  展開された状態のポリシーは削除できません。 右クリック**ProcessPurchaseOrder**、順にクリックします**Undeploy**ポリシーの展開を解除します。 **削除**ポリシーが展開時に、メニュー項目が表示されます。  
  
    > [!NOTE]
    >  ボキャブラリ、 **ProcessPurchaseOrder**ここでポリシーが依存**POVocabulary**も削除されます。  
  
    > [!NOTE]
    >  アプリケーションからポリシーを削除すると、そのポリシーと依存対象のボキャブラリは、アプリケーションからだけでなくルール エンジン データベースからも削除されます。  
  
#### <a name="to-import-the-xml-file-to-re-create-the-processpurchaseorder-policy"></a>XML ファイルをインポートして ProcessPurchaseOrder ポリシーを再作成するには  
  
1. BizTalk Server 管理コンソールで **コンソール ルート**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、順に展開**BizTalk グループ**します。  
  
2. 右クリック**アプリケーション**、 をポイント**インポート**、 をクリックし、**ポリシー**します。  
  
3. 参照、および XML ファイルをダブルクリックします (**C:\BRE-Walkthroughs\ProcessPOFromAdmin.xml**)、最初の手順で作成しました。  
  
4. 展開**\<すべての成果物\>** **アプリケーション**します。  
  
5. クリックして**ポリシー**のバージョン 1.3 を確認する必要があります、 **ProcessPurchaseOrder**が一覧にします。  
  
6. F5 キーを押してビューを更新します。 **ProcessPurchaseOrder**にする必要があります、**非公開**状態。  
  
#### <a name="to-add-the-processpurchaseorder-policy-to-the-ruletestapp-application"></a>RuleTestApp アプリケーションに ProcessPurchaseOrder ポリシーを追加するには  
  
1.  BizTalk Server 管理コンソールで、右クリック**ProcessPurchaseOrder**ポリシー、およびクリック**発行**します。  
  
    > [!NOTE]
    >  BizTalk アプリケーションに追加できるのは、公開済みのポリシーだけです。  
  
2.  **アプリケーション**ノード展開**RuleTestApp**します。  
  
3.  クリックして**ポリシー**で**RuleTestApp**します。  
  
4.  右側の一覧内を右クリックし、[**追加**、] をクリックし、**ポリシー**します。  
  
5.  展開、 **ProcessPurchaseOrder**ノードを選択、チェック ボックスを**バージョン 1.3 (Published)**、順にクリックします**OK**します。 .  
  
6.  右クリック**ProcessPurchaseOrder**、 をクリックし、**デプロイ**します。 表示されない場合**ProcessPurchaseOrder**一覧で、f5 キーを押して表示を更新します。  
  
7.  クリックして**はい**確認のメッセージ ボックスにします。  
  
## <a name="procedures-for-deploying-the-policy-by-using-an-msi-file"></a>MSI ファイルを使用したポリシーの展開手順  
  
#### <a name="to-export-the-ruletestapp-application-to-an-msi-file"></a>RuleTestApp アプリケーションを MSI ファイルにエクスポートするには  
  
1. **開始**] メニューの [open **BizTalk Server 管理**します。 このツールを既に開いている場合は、F5 キーを押して更新します。  
  
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
    >  RuleTestApp アプリケーションをエクスポートすると、アプリケーションで使用されるポリシーとボキャブラリも MSI ファイルにエクスポートされます。 後で MSI ファイルをインポートすると、ボキャブラリ、ポリシー、およびアプリケーションが、すべて再作成されます。  
  
#### <a name="to-delete-the-ruletestapp-application"></a>RuleTestApp アプリケーションを削除するには  
  
1.  BizTalk Server 管理コンソールで、右クリック**RuleTestApp**、確認の場合と、**削除**メニューを有効または無効になっています。  
  
2.  場合**削除**は右クリックし、無効になっています**RuleTestApp**、 をクリック**停止**を選択します**完全停止 - インスタンスの終了**、順にクリックします。**停止**します。  
  
3.  右クリック**RuleTestApp**、 をクリックし、**削除**します。  
  
4.  クリックして**はい**削除を確定します。  
  
    > [!NOTE]
    >  アプリケーションを削除すると、アプリケーション内のすべてのポリシーとそれらが依存するボキャブラリも、ルール エンジン データベースから削除されます。  
  
#### <a name="to-verify-that-the-processpurchaseorder-policy-and-povocabulary-vocabulary-are-deleted"></a>ProcessPurchaseOrder ポリシーと POVocabulary ボキャブラリが削除されたことを確認するには  
  
1.  **開始**] メニューの [open**ビジネス ルール作成ツール**します。 既にを開き、更新、f5 キーを押してのビジネス ルール作成ツールの場合は。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**します。  
  
2.  ポリシー エクスプ ローラー ウィンドウで、**ポリシー**、ProcessPurchaseOrder ポリシーが存在しないことを確認します。  
  
3.  ファクト エクスプ ローラー ウィンドウで、**ボキャブラリ**POVocabulary が存在しないことを確認します。  
  
#### <a name="to-import-the-msi-file-to-re-create-the-ruletestapp-application"></a>MSI ファイルをインポートして RuleTestApp アプリケーションを再作成するには  
  
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
  
1.  **開始**] メニューの [open**ビジネス ルール作成ツール**します。 既に開いている場合は、F5 キーを押して更新します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**します。  
  
2.  ポリシー エクスプ ローラー ウィンドウで、**ポリシー**、ことを確認および**ProcessPurchaseOrder**存在します。  
  
3.  ファクト エクスプ ローラー ウィンドウで、**ボキャブラリ**、ことを確認および**POVocabulary**存在します。  
  
#### <a name="to-test-the-solution"></a>ソリューションをテストするには、次の操作を行います。  
  
1. **開始**] メニューの [open **BizTalk Server 管理**します。 BizTalk Server 管理コンソールを既に開いている場合は、F5 キーを押して更新します。  
  
2. 展開**コンソール ルート**、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、順に展開**アプリケーション**します。  
  
3. 右クリック**RuleTestApp**、 をクリックし、**開始**します。  
  
4. クリックして**開始**します。  
  
5. コピー **SamplePO.xml**で作成した[チュートリアル: ポリシーのテスト](../core/walkthrough-testing-the-policy.md)オーケストレーションの入力ディレクトリにします。  
  
6. オーケストレーションの出力ディレクトリに、出力ファイルが表示されます。 出力 XML ファイルを開き、注意の値、**状態**にフィールドが設定されている**Approved**します。  
  
7. 手順 3. と 4. を繰り返します**SamplePO2.xml**、いることを確認しの値、**状態**出力ドキュメント内のフィールドは、入力ドキュメントと同じ (**XYZ**)。  
  
## <a name="comments"></a>コメント  
  
-   **非常に重要な**ことに注意して、アプリケーションからポリシーを削除するときをだけを削除しないアプリケーションとポリシー間の関連付けは、するも、ポリシーとその関連付けられたボキャブラリをルールから削除エンジンのデータベースです。  
  
-   既定では、アプリケーションを開始すると、ポリシーが自動的に展開されます。 同様に、アプリケーションを停止し、選択する**完全停止 - インスタンスを終了**、関連付けられているポリシーは展開解除に自動的にします。 選択すると**部分停止 - 実行中のインスタンスを中断**、関連付けられているポリシーが解除されません自動的にします。  
  
-   ビジネス ルール作成ツールと BizTalk Server 管理コンソールで操作を実行する前には、ビューを更新して、最新の情報を確実に表示してください。  
  
-   以前のバージョンが BizTalk アプリケーションに関連付けられているポリシーに、新しいバージョンを作成する場合、ポリシーの新しいバージョンを手動でアプリケーションに追加してください。 ルール エンジン データベースから削除する場合を除いて、ポリシーの古いバージョンは削除しないでください。  
  
-   インポート前に、複数の BRL (ビジネス ルール言語 XML ファイル) ファイルを単一の BRL ファイルに結合できます。 次のコードは 3 つの BRL ファイルを示しています。 最初の BRL ファイルに含まれる、 **POVocabulary**ボキャブラリです。 2 番目の BRL ファイルに含まれる、 **ProcessPurchaseOrder**ポリシー。 3 番目の BRL ファイルには、両方が含まれています、 **POVocabulary**ボキャブラリと**ProcessPurchaseOrder**ポリシー。 3 番目の BRE ファイルを作成するには、次の手順を実行します。  
  
    1.  エディターの任意のファイルを使用して新しいファイルを作成し、XML ファイルとして保存します (例: POPolicyVocabulary.xml)。  
  
    2.  ボキャブラリが含まれている 1 番目の BRL ファイルから、XML コンテンツ全体をコピーします。  
  
    3.  ルール セット ブロックのコピー (で始まる、 \<ruleset\>タグと末尾には、 \</ruleset\>タグ)、2 番目の BRL ファイルから。  
  
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