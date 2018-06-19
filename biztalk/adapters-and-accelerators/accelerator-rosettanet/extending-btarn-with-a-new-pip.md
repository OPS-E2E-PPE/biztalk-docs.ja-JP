---
title: 新しい PIP による BTARN の拡張 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BTARN, extending functionality
- PIPs, extending BTARN
- BTARN, PIPs
ms.assetid: 3db5cd5c-031f-4451-9be5-4b5d6163c3b1
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2b1fca61cd40b932e53b2908603a225d3980fa1
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007177"
---
# <a name="extending-btarn-with-a-new-pip"></a>新しい PIP による BTARN の拡張
このトピックを拡張する方法について説明[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]新しいプロセス PIP (Partner Interface) スキーマを使用します。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] を拡張すると、RosettaNet PIP が BTARN セットアップ プログラムによってインストールされるどのスキーマとも関連付けられていない場合に、その PIP に基づくスキーマを追加できるようになります。  
  
 新しい PIP で [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] を拡張するには、新しいスキーマを独自のアセンブリで展開します。 また、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] RNPIP アセンブリ内に展開された既存のスキーマを変更することもできます。 詳細については、次を参照してください。 [Rnpip の既存の PIP 変更](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md)です。  
  
### <a name="to-extend-btarn-with-a-new-pip"></a>BTARN を新しい PIP で拡張するには  
  
1.  をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
2.  コマンド プロンプトでに移動\<*ドライブ*\>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk 2013 Accelerator for rosettanet \sdk\utilities\schema Generator です。  
  
3.  コマンド プロンプトで次のように入力します。 **CScript InstallDTD.vbs**、キーを押します**Enter**です。  
  
    > [!NOTE]
    >  BizTalk Server をインストールした後に、手順 1 ~ 3 を 1 回実行する必要がのみです。  
  
4.  Visual Studio を起動します。  
  
5.  **[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。  
  
6.  新しいプロジェクト ダイアログ ボックスで、次のように選択します。 **BizTalk プロジェクト**をクリックして、左側のウィンドウ**空の BizTalk Server プロジェクト**右側のウィンドウでします。  
  
7.  をクリックして**参照**プロジェクトを保存するディレクトリをポイントします。  
  
8.  **名**ボックスで、プロジェクト名を入力します。 **MyCustomPIP**、順にクリック**OK**です。  
  
9. Visual Studio コマンド プロンプトを起動します。  
  
10. コマンド プロンプトでは、手順 7. の種類で入力した場所に移動**sn-k\<プロジェクト name.snk\>**、キーを押します**Enter**です。  
  
11. ソリューション エクスプ ローラーでプロジェクト名を右クリックし、をクリックして**プロパティ**です。  
  
12. **プロパティ ページ**ダイアログ ボックスで、をクリックして**アセンブリ****共通プロパティ**左側のウィンドウでします。  
  
13. 右側のペインで下にスクロール**厳密名**、 をクリックして**アセンブリ キー ファイル**、右側のウィンドウで、省略記号ボタン (...) をクリックします。 手順 7. で入力した場所に移動し、手順 10. で作成した .snk ファイルの名前を選択します。  
  
14. プロパティ ページ ダイアログ ボックスで、展開**構成プロパティ**、クリックして**展開**です。 右側のウィンドウでをクリックして**再展開**を選択`True`、順にクリック**OK**です。  
  
15. ソリューション エクスプ ローラーでプロジェクト名を右クリックし、**追加**、クリックして**既存項目の**します。  
  
16. **既存項目の追加** ダイアログ ボックスに移動\<*ドライブ*\>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk 2013 Accelerator for rosettanet \sdk\schemas、選択**xml.xsd**をクリックし、**追加**です。  
  
17. RNPIP の拡張に使用する PIP を RosettaNet.org からダウンロードします。詳細については、次を参照してください。[新しい Partner Interface Process の組み込み](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md)です。  
  
18. ソリューション エクスプ ローラーでプロジェクト名を展開しを右クリックして**参照**、クリックして**参照の追加**です。  
  
19. **参照の追加**ダイアログ ボックスで、をクリックして**参照**に移動する\<*ドライブ*\>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk 2013 Accelerator for rosettanet \bin し選択**Microsoft.Solutions.BTARN.Schemas.RNPIPs.dll**です。 をクリックして**開く**、順にクリック**OK**です。  
  
20. ソリューション エクスプ ローラーでプロジェクト名を右クリックし、**追加**、クリックして**生成した項目の追加**です。  
  
21. **生成した項目の追加** ダイアログ ボックスで、**カテゴリ** ウィンドウで、をクリックして**スキーマの生成**です。 **テンプレート** ウィンドウで、をクリックして**スキーマの生成**、クリックして**追加**です。  
  
22. [スキーマの生成] ダイアログ ボックスで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**ドキュメントの種類**|選択**DTD スキーマ**です。|  
    |**入力ファイル**|をクリックして**参照**を RosettaNet.org から DTD ファイルが含まれているフォルダーに移動し、をクリックし、DTD ファイルを選択**開く**です。|  
  
23. [スキーマの生成] ダイアログ ボックスで、 **OK**です。  
  
24. ソリューション エクスプローラーで、インポートした .xsd ファイルをダブルクリックします。  
  
25. BizTalk エディターで、選択、 \<*スキーマ*\>ノード。  
  
26. [プロパティ] ウィンドウでスクロールして**ドキュメントの種類**です。 **ドキュメントの種類**ボックスで、 **PIP**\<*3 桁のコード*\>など、 **PIP3A2**です。 **ドキュメント バージョン**ボックスに、入力**v**\<*xx.xx* \>または**R** \< *xx.xx*\>など、 **R01.02**です。 このバージョン番号は、RosettaNet PIP 仕様に記載されています。  
  
27. [プロパティ] ウィンドウでスクロールして**ルート参照**です。 をクリックして**ルート参照**、ドロップダウン リストから、スキーマ、たとえば、select のルート ノードを選択して **[pip3c5billingstatementnotification]** です。  
  
28. [プロパティ] ウィンドウで、スクロールまで**Target Namespace**です。 **Target Namespace**、型**http://schemas.microsoft.com/biztalk/btarn/2004/\<DTD ファイル名\>.dtd**DTD ファイル名はたとえば、 **3C5_MS_R01_00_BillingStatementNotification.dtd**です。  
  
    > [!NOTE]
    >  BTARN では、ターゲットの名前空間にこの命名規則を使用する必要があります。 別の名前空間規則を使用する場合[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]PIP ドキュメントのスキーマ検証を処理しません。  
  
    > [!NOTE]
    >  ターゲットの名前空間プロパティの DTD ファイル名には、PIP のバージョン番号が使用されています。 そのため、同じ PIP コードの複数のバージョンを使用できます。  
  
29. [プロパティ] ウィンドウで、スクロールまで**Imports**です。 横にある省略記号ボタン (...) をクリックして**Imports**、クリックして**追加**です。  
  
30. **BizTalk 型の選択**] ダイアログ ボックスで、展開\<*プロジェクト名*\>、展開**参照**、展開**Microsoft.Solutions.BTARN.Schemas.RNPIPs**、展開**スキーマ**[ **Microsoft.Solutions.BTARN.Schemas.RNPIPs.BaseDataTypes**をクリックして **[ok]**、クリックして**OK**もう一度です。  
  
31. プロジェクト名を右クリックし、をクリックして**展開**です。  
  
32. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
33. BizTalk 管理コンソールで、展開**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **(ローカル)** の順に展開および**ホスト**です。 **ホスト**をクリックして**BizTalkServerApplication**です。  
  
34. 右側のウィンドウで、ホストの名前を右クリックし、をクリックして**再起動**です。  
  
    > [!NOTE]
    >  新しくインポートした PIP で RNPIP を拡張したら、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理コンソールでその PIP を使用して、正しい PIP 設定とアグリーメントを作成する必要があります。  
  
## <a name="see-also"></a>参照  
 [新しい Partner Interface Process の組み込み](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md)   
 [Pip の操作](../../adapters-and-accelerators/accelerator-rosettanet/working-with-pips.md)   
 [RNPIP の既存の PIP の変更](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md)