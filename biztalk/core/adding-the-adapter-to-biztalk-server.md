---
redirect_url: /biztalk/core/adding-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: e075bfbfdb082887ea746ee81e24a5176d9ad98d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976603"
---
# <a name="adding-the-adapter-to-biztalk-server"></a>BizTalk Server にアダプターの追加
Microsoft BizTalk Adapter for JD Edwards OneWorld には、受信ハンドラーと送信ハンドラーの両方のフォルダーが含まれています。 送信ハンドラー フォルダーには、BizTalkServerApplication が含まれています。 BizTalk Adapter for JD Edwards OneWorld は作成可能です。BizTalk Server とインプロセスで実行され、分離されたホスト プロセスでは実行されません。  
  
 BizTalk Server にアダプターを追加するには、次の手順を実行します。  
  
### <a name="to-add-biztalk-adapter-for-jd-edwards-oneworld"></a>BizTalk Adapter for JD Edwards OneWorld を追加するには  
  
1. **開始**メニューで、 **Program Files**、 をポイント[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリックします**BizTalk Server 管理**を開始する、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
2. 展開**BizTalk Server 管理**、展開**BizTalk グループ**、順に展開**プラットフォームの設定**します。  
  
3. 右クリックして**アダプター**、 をポイント**新規**、 をクリック**アダプター**します。  
  
4. **アダプター プロパティ** ダイアログ ボックスで、アダプターの名前を入力します。 たとえば、JDEdwards です。  
  
5. 選択 **[jdeoneworld]** から、**アダプター**ボックスの一覧をクリックして**OK**します。  
  
## <a name="verifying-the-adapter"></a>アダプターの確認  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、調べることで、アダプターが正しく機能していること確認できます、**論理システム**ウィンドウ。 初回のインストレーションでは、このウィンドウは空です。これは、サーバー システムへの接続が未確立で、論理システムが作成されていないからです。  
  
#### <a name="to-verify-that-the-adapter-is-running-correctly"></a>アダプターが正常に動作していることを確認するには  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 **BizTalk グループ**、展開**プラットフォームの設定**、展開**アダプター**、し、 **[Jdeoneworld]** します。  
  
2. 詳細ペインで右クリックして**BizTalkServerApplication**を選択し、**プロパティ**します。  
  
3. **[プロパティ]** タブをクリックします。  
  
4. SQL 接続パラメーターを設定します。  
  
   -   **SQL データベース パラメーターを定義する**SQL Server 名とデータベースはインストール時に設定するものです。 これは、サーバーと、このアダプターのデータベースを再定義できますをテキスト領域です。  
  
5. クリックして**閉じる**を終了する、**論理システム**ウィンドウ。  
  
    次のステップでは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用して論理システムを追加します。  
  
## <a name="see-also"></a>参照  
 [計画とアーキテクチャ](../core/planning-and-architecture17.md)   
 [BizTalk Adapter for JD Edwards OneWorld のセキュリティ](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)   
 [BizTalk Adapter for JD Edwards OneWorld の追加](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)