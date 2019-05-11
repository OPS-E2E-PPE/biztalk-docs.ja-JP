---
title: 手順 1:Siebel アダプターと vPrev BizTalk プロジェクトの変更 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7bd95e2-bd51-420f-8156-6f17cc0e91d6
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68a3bc43e3f8f946652b75768c1846a388a28c13
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370904"
---
# <a name="step-1-modify-the-vprev-biztalk-project-with-the-siebel-adapter"></a>手順 1:Siebel アダプターと vPrev BizTalk プロジェクトの変更します。
![ステップ 1/3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")  
  
 **所要時間:** 10 分  
  
 **目標:** この手順では、既存の vPrev BizTalk プロジェクトに、次の変更を行います。  
  
- WCF ベースを使用してアカウントのビジネス コンポーネントに対する挿入操作のメタデータを生成[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。  
  
- WCF ベースを使用して挿入操作を実行するための vPrev Siebel アダプターの要求メッセージを使用して挿入操作を実行するための要求メッセージにマップ[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。  
  
- WCF ベースを使用して受信応答メッセージにマップ[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]vPrev Siebel アダプターの応答メッセージにします。  
  
## <a name="prerequisite"></a>前提条件  
  
-   Siebel システムでアカウントのビジネス コンポーネントに対して、挿入操作を実行する vPrev BizTalk プロジェクトが必要です。  
  
### <a name="to-modify-the-vprev-biztalk-project"></a>VPrev BizTalk プロジェクトを変更するには  
  
1. WCF ベースを使用してアカウントのビジネス コンポーネントに対する挿入操作のメタデータを生成[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。 使用することができます、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]メタデータを生成します。  
  
    メタデータを生成する方法の詳細については、次を参照してください。 [Visual Studio で Siebel 操作のメタデータの取得](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)します。 スキーマを生成すると後のような名前のファイル*SiebelBindingSchema.xsd* BizTalk プロジェクトに追加されます。 このファイルには、WCF ベースを使用してアカウントのビジネス コンポーネントに対する挿入操作を実行するメッセージを送信するためのスキーマが含まれています。[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。  
  
2. 挿入操作のメタデータを生成すると、ポートのバインド ファイルも作成します。 次の手順で Siebel システムへのメッセージを送信する Wcf-custom 送信ポートを作成するこのバインド ファイルが使用されます。 操作の SOAP アクションは、メタデータの生成対象の操作にも設定されます。 たとえば、挿入操作のメタデータを生成すると、送信ポートでの SOAP アクションで、操作名が、"Insert"になります。 ただし、操作名とオーケストレーションの一部異なる可能性があります、たとえば、作成した論理送信ポートで"Operation_1"。 その結果、送信ポートを使用して Siebel システムにメッセージを送信するときに、エラーが発生します。 これを回避するには、ことを確認しますで論理送信ポート、オーケストレーションでは、メタデータを生成する操作名と同じ操作名。  
  
    そのため、このチュートリアルが発生した場合、挿入操作のメタデータを生成するための名前を変更"Insert"する論理送信ポートの操作。  
  
3. 要求メッセージは、WCF ベースを使用して生成されたスキーマに vPrev Siebel アダプターを使用して生成されたスキーマをマップ[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。  
  
   1. BizTalk マッパーは、BizTalk プロジェクトに追加します。 BizTalk プロジェクトを右クリックし、[**追加**、] をクリック**新しい項目の**します。  
  
       **新しい項目の追加**ダイアログ ボックスで、左側のウィンドウから**マップ ファイル**します。 右側のウィンドウから次のように選択します。**マップ**します。 マップの名前を指定します。 **RequestMap.btm**します。 **[追加]** をクリックします。  
  
   2. 送信元スキーマ ペインで、次のようにクリックします。**ソース スキーマを開く**します。  
  
   3. **BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**、vPrev Siebel アダプターの要求メッセージのスキーマを選択します。 このチュートリアルでは、次のように選択します。 *Siebel_BussComp_Migration.AccountService_Account_x5d*します。 **[OK]** をクリックします。  
  
   4. **送信元スキーマのルート ノード**ダイアログ ボックスで、*挿入*、順にクリックします**OK**します。  
  
   5. 送信先スキーマ ペインで、次のようにクリックします。**送信先スキーマを開く**します。  
  
   6. **BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**、WCF ベースの要求メッセージのスキーマを選択して[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。 このチュートリアルでは、次のように選択します。 *Siebel_BussComp_Migration.SiebelDBBindingSchema*、 をクリックし、 **OK**します。  
  
   7. **ターゲット スキーマのルート ノード**ダイアログ ボックスで、*挿入*、順にクリックします**OK**します。  
  
   8. 両方のスキーマでは、次の要素をマップします。**Currency_Code**、 **Current_Volume**、 **Customer_Account_Group**、**場所**、 **Main_Phone_Number**、 **名前**、 **Party_Name**、 **Primary_Address_Id**、  
  
   9. マップを保存します。  
  
4. 応答メッセージは、WCF ベースを使用して生成されたスキーマに vPrev Siebel アダプターを使用して生成されたスキーマをマップ[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。  
  
   1. BizTalk マッパーは、BizTalk プロジェクトに追加します。 BizTalk プロジェクトを右クリックし、[**追加**、] をクリック**新しい項目の**します。  
  
       新しい項目の追加 ダイアログ ボックスの左側のウィンドウから次のように選択します。**マップ ファイル**します。 右側のウィンドウから次のように選択します。**マップ**します。 マップの名前を指定します。 **ResponseMap.btm**します。 **[追加]** をクリックします。  
  
   2. 送信元スキーマ ペインで、次のようにクリックします。**ソース スキーマを開く**します。  
  
   3. **BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**、WCF ベースの応答メッセージのスキーマを選択して[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。 このチュートリアルでは、次のように選択します。 *Siebel_BussComp_Migration.SiebelDBBindingSchema*します。 **[OK]** をクリックします。  
  
   4. **送信元スキーマのルート ノード**ダイアログ ボックスで、 *InsertResponse*  をクリック**OK**します。  
  
   5. 送信先スキーマ ペインで、次のようにクリックします。**送信先スキーマを開く**します。  
  
   6. **BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**、vPrev Siebel アダプターの応答メッセージのスキーマを選択します。 このチュートリアルでは、次のように選択します。 *Siebel_BussComp_Migration.AccountService_Account_x5d*します。 **[OK]** をクリックします。  
  
   7. **ターゲット スキーマのルート ノード**ダイアログ ボックスで、 *InsertResponse*  をクリック**OK**します。  
  
   8. マップ、 **: 文字列の配列**送信元スキーマ内の要素、**公開: 文字列**次の図に示すように、送信先スキーマ内の要素。  
  
       ![アダプター バージョン間の応答メッセージをマップ](../../adapters-and-accelerators/adapter-siebel/media/6352035b-79c0-4850-a8f7-e4f6581c8532.gif "6352035b-79c0-4850-a8f7-e4f6581c8532")  
  
   9. マップを保存します。  
  
5. 保存し、BizTalk ソリューションをビルドします。 クリックして、ソリューションを右クリックして**ソリューションのビルド**します。  
  
6. ソリューションを展開する。 クリックして、ソリューションを右クリックして**ソリューションの配置**します。  
  
## <a name="next-steps"></a>次の手順  
 Wcf-custom 送信ポートを作成および構成」の説明に従って、この手順で作成したマップを使用するように[手順 2。Oracle データベース アダプターを使用する BizTalk Server 管理コンソールでオーケストレーションを構成](../../adapters-and-accelerators/adapter-oracle-database/step-2-configure-an-orchestration-to-use-the-oracle-db-adapter-in-biztalk.md)します。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 2: Siebel の BizTalk プロジェクトの移行](../../adapters-and-accelerators/adapter-siebel/tutorial-2-migrating-biztalk-projects-in-siebel.md)