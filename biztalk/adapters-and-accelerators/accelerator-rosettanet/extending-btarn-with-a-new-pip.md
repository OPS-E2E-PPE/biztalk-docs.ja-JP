---
title: 新しい PIP による BTARN の拡張 |Microsoft Docs
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
ms.openlocfilehash: 0904d6d427fb6c04ae911edf23edb653ba9cb734
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003651"
---
# <a name="extending-btarn-with-a-new-pip"></a>新しい PIP による BTARN の拡張
このトピックでは、Microsoft を拡張する方法を説明します。[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]新しいパートナー インターフェイス Process (PIP) スキーマを使用します。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] を拡張すると、RosettaNet PIP が BTARN セットアップ プログラムによってインストールされるどのスキーマとも関連付けられていない場合に、その PIP に基づくスキーマを追加できるようになります。  

 新しい PIP で [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] を拡張するには、新しいスキーマを独自のアセンブリで展開します。 また、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] RNPIP アセンブリ内に展開された既存のスキーマを変更することもできます。 詳細については、次を参照してください。 [Rnpip の既存の PIP 変更](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md)します。  

### <a name="to-extend-btarn-with-a-new-pip"></a>BTARN を新しい PIP で拡張するには  

1. をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  

2. コマンド プロンプトに移動します。 \<*ドライブ*\>: \Program Files\\Microsoft の BizTalk 2013 Accelerator for rosettanet \sdk\utilities\schema Generator します。  

3. コマンド プロンプトで「 **CScript InstallDTD.vbs**キー押しますと **」と入力**します。  

   > [!NOTE]
   >  BizTalk Server をインストールした後、手順 1 ~ 3 を 1 回実行する必要がありますのみです。  

4. Visual Studio を起動します。  

5. **[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。  

6. 新しいプロジェクト ダイアログ ボックスで、次のように選択します。 **BizTalk プロジェクト**で、左側のウィンドウとクリック**空の BizTalk Server プロジェクト**右側のウィンドウでします。  

7. クリックして**参照**プロジェクトを保存するディレクトリをポイントするとします。  

8. **名前**ボックスに、プロジェクト名を入力します。 **MyCustomPIP**、順にクリックします**OK**します。  

9. Visual Studio コマンド プロンプトを起動します。  

10. コマンド プロンプトで、7 種類の手順で入力した場所に移動します。 **sn-k \<name.snk プロジェクト\>**、およびキーを押します **」と入力**します。  

11. ソリューション エクスプ ローラーでプロジェクト名を右クリックし をクリックし、**プロパティ**します。  

12. **プロパティ ページ**ダイアログ ボックスで、をクリックして**アセンブリ****共通プロパティ**左側のウィンドウでします。  

13. 右側のペインでスクロールして**厳密な名前**、 をクリックして**アセンブリ キー ファイル**、右側のウィンドウで省略記号ボタン (…) を順にクリックします。 手順 7. で入力した場所に移動し、手順 10. で作成した .snk ファイルの名前を選択します。  

14. プロパティ ページ ダイアログ ボックスで、**構成プロパティ**、 をクリックし、**展開**します。 右側のウィンドウで次のようにクリックします。**再デプロイ**を選択します`True`、順にクリックします**OK**します。  

15. ソリューション エクスプ ローラーでプロジェクト名を右クリックして**追加**、 をクリックし、**既存項目の**します。  

16. **既存項目の追加** ダイアログ ボックスに移動\<*ドライブ*\>: \Program Files\\Microsoft の BizTalk 2013 Accelerator for rosettanet \sdk\schemas を選択します**xml.xsd**、 をクリックし、**追加**します。  

17. RNPIP の拡張に使用する PIP を RosettaNet.org からダウンロードします。詳細については、次を参照してください。[新しい Partner Interface Process の組み込み](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md)します。  

18. ソリューション エクスプ ローラーでプロジェクト名を展開し、右クリックして**参照**、 をクリックし、**参照の追加**します。  

19. **参照の追加**ダイアログ ボックスで、をクリックして**参照**に移動し、 \<*ドライブ*\>: \Program Files\\Microsoft BizTalk 2013Accelerator for rosettanet \bin を選択し**Microsoft.Solutions.BTARN.Schemas.RNPIPs.dll**します。 をクリックして**オープン**、順にクリックします**OK**します。  

20. ソリューション エクスプ ローラーでプロジェクト名を右クリックして**追加**、 をクリックし、**生成した項目の追加**します。  

21. **生成した項目の追加** ダイアログ ボックスで、**カテゴリ**ウィンドウで、をクリックして**スキーマの生成**します。 **テンプレート**ウィンドウで、をクリックして**スキーマの生成**、 をクリックし、**追加**します。  

22. [スキーマの生成] ダイアログ ボックスで、次の操作を行います。  


    |     プロパティ      |                                                                    目的                                                                    |
    |-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
    | **ドキュメントの種類** |                                                              選択**DTD スキーマ**します。                                                              |
    |  **入力ファイル**   | クリックして**参照**RosettaNet.org からダウンロードした DTD ファイルが含まれているフォルダーに移動し、をクリックし、DTD ファイルを選択して、**オープン**します。 |


23. スキーマの生成] ダイアログ ボックスで、[ **OK**します。  

24. ソリューション エクスプローラーで、インポートした .xsd ファイルをダブルクリックします。  

25. BizTalk エディターで、選択、 \<*スキーマ*\>ノード。  

26. [プロパティ] ウィンドウでスクロールして**ドキュメントの種類**します。 **ドキュメントの種類**ボックスで、 **PIP**\<*3 桁のコード*\>、たとえば、 **PIP3A2**します。 **ドキュメント バージョン**ボックスに「 **v**\<*xx.xx* \>または**R** \< *xx.xx*\>、たとえば、 **R01.02**します。 このバージョン番号は、RosettaNet PIP 仕様に記載されています。  

27. [プロパティ] ウィンドウでスクロールして**ルート参照**します。 クリックして**ルート参照**、ドロップダウン リストから、スキーマ、たとえば、select のルート ノードを選択します。 **[pip3c5billingstatementnotification]** します。  

28. 最大スクロール プロパティ ウィンドウで**Target Namespace**します。 **Target Namespace**、型<strong>http://schemas.microsoft.com/biztalk/btarn/2004/\<DTDファイル名\>.dtd</strong>など、DTD ファイル名がある場合、 **3C5_MS_R01_00_BillingStatementNotification.dtd**.  

    > [!NOTE]
    >  BTARN では、ターゲットの名前空間にこの命名規則を使用する必要があります。 名前空間の別の規則を使用する場合[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]PIP ドキュメントのスキーマ検証を処理しません。  
    > 
    > [!NOTE]
    >  ターゲットの名前空間プロパティの DTD ファイル名には、PIP のバージョン番号が使用されています。 そのため、同じ PIP コードの複数のバージョンを使用できます。  

29. 最大スクロール プロパティ ウィンドウで**Imports**します。 横にある省略記号ボタン (…) をクリックします。 **Imports**、 をクリックし、**追加**します。  

30. **BizTalk 型の選択** ダイアログ ボックスで、展開\<*プロジェクト名*\>、展開**参照**、展開**Microsoft.solutions.btarn.schemas.rnpips**、展開**スキーマ**、 **Microsoft.Solutions.BTARN.Schemas.RNPIPs.BaseDataTypes**、 をクリックして**OK**、 をクリックし、 **OK**もう一度です。  

31. プロジェクト名を右クリックし、**デプロイ**します。  

32. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリックします**BizTalk Server 管理**します。  

33. BizTalk 管理コンソールで  **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **(Local)**、順に展開**ホスト**します。 [**ホスト**、] をクリックして**BizTalkServerApplication**します。  

34. 右側のウィンドウで、ホストの名前を右クリックし をクリックし、**再起動**します。  

    > [!NOTE]
    >  新しくインポートした PIP で RNPIP を拡張したら、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理コンソールでその PIP を使用して、正しい PIP 設定とアグリーメントを作成する必要があります。  

## <a name="see-also"></a>参照  
 [新しい Partner Interface Process の組み込み](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md)   
 [Pip の操作](../../adapters-and-accelerators/accelerator-rosettanet/working-with-pips.md)   
 [RNPIP の既存の PIP の変更](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md)