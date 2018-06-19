---
title: '手順 1: 変更の Siebel アダプターと BizTalk プロジェクト vPrev |Microsoft ドキュメント'
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
ms.openlocfilehash: 5465a80fd7b75dcbf7ec864b196d2fd5033cb003
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224066"
---
# <a name="step-1-modify-the-vprev-biztalk-project-with-the-siebel-adapter"></a>手順 1: Siebel アダプターと vPrev BizTalk プロジェクトを変更します。
![手順 1/3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")  
  
 **所要時間:** 10 分  
  
 **目標:** このステップで、次を変更する既存の vPrev BizTalk プロジェクト。  
  
-   WCF ベースを使用してアカウントのビジネス コンポーネントに対する挿入操作のメタデータを生成[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。  
  
-   WCF ベースを使用する挿入操作を実行するための要求メッセージに vPrev Siebel アダプターを使用して挿入操作を実行するための要求メッセージにマップ[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。  
  
-   WCF ベースを使用して受信した応答メッセージをマップ[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]vPrev Siebel アダプターの応答メッセージにします。  
  
## <a name="prerequisite"></a>前提条件  
  
-   Siebel システムでアカウント ビジネス コンポーネントには挿入操作を実行する vPrev BizTalk プロジェクトが必要です。  
  
### <a name="to-modify-the-vprev-biztalk-project"></a>VPrev BizTalk プロジェクトを変更するには  
  
1.  WCF ベースを使用してアカウントのビジネス コンポーネントに対する挿入操作のメタデータを生成[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。 使用することができます、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]メタデータを生成します。  
  
     メタデータを生成する方法については、次を参照してください。 [Siebel 操作の Visual Studio でのメタデータを取得](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)です。 スキーマを生成すると後のような名前のファイルが*SiebelBindingSchema.xsd*が BizTalk プロジェクトに追加します。 このファイルには、WCF ベースを使用してアカウントのビジネス コンポーネントに対する挿入操作を実行するメッセージを送信するためのスキーマが含まれています。[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。  
  
2.  挿入操作のメタデータを生成すると、ポートのバインド ファイルも作成されます。 次の手順で Siebel システムへのメッセージを送信する Wcf-custom 送信ポートを作成するこのバインド ファイルが使用されます。 操作の SOAP アクションは、メタデータを生成する操作にも設定されます。 たとえば、挿入操作のメタデータを生成する場合、送信ポートでの SOAP アクションで、操作名されます"Insert"。 ただし、操作の名前、オーケストレーションの一部異なる場合があります、たとえばなどを作成する論理送信ポートで"Operation_1"。 結果として、送信ポートを使用して、Siebel システムにメッセージを送信するときに、エラーを取得します。 これを防ぐためには、確認の論理送信ポート、オーケストレーションでは、メタデータの生成対象の操作名と同じ操作名。  
  
     そのため、このチュートリアルが発生した場合、挿入操作のメタデータを生成するための名前を変更"Insert"への論理送信ポート操作します。  
  
3.  要求メッセージの WCF ベースを使用して生成されたスキーマに vPrev Siebel アダプターを使用して生成されたスキーマにマップ[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。  
  
    1.  BizTalk マッパーは、BizTalk プロジェクトに追加します。 BizTalk プロジェクトを右クリックし、[**追加**、] をクリック**新しい項目の**します。  
  
         **新しい項目の追加**ダイアログ ボックスで、左ペインで、**マップ ファイル**です。 右側のウィンドウから次のように選択します。**マップ**です。 など、マップの名前を指定**RequestMap.btm**です。 **[追加]** をクリックします。  
  
    2.  送信元スキーマ ペインで、をクリックして**ソース スキーマを開く**です。  
  
    3.  **BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**、vPrev Siebel アダプターの要求メッセージのスキーマを選択します。 このチュートリアルでは、次のように選択します。 *Siebel_BussComp_Migration.AccountService_Account_x5d*です。 **[OK]** をクリックします。  
  
    4.  **送信元スキーマのルート ノード**ダイアログ ボックスで、*挿入*、順にクリック**OK**。  
  
    5.  送信先スキーマ ペインで、をクリックして**送信先スキーマを開く**です。  
  
    6.  **BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**、WCF ベースの要求メッセージのスキーマを選択して[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。 このチュートリアルでは、次のように選択します。 *Siebel_BussComp_Migration.SiebelDBBindingSchema*、クリックして**OK**です。  
  
    7.  **ターゲット スキーマのルート ノード**ダイアログ ボックスで、*挿入*、順にクリック**OK**です。  
  
    8.  両方のスキーマで、次の要素をマップ: **Currency_Code**、 **Current_Volume**、 **Customer_Account_Group**、**場所**、**Main_Phone_Number**、**名前**、 **Party_Name**、 **Primary_Address_Id**、  
  
    9. マップを保存します。  
  
4.  応答メッセージの vPrev Siebel アダプターは WCF ベースを使用して生成されたスキーマを使用して生成されたスキーマにマップ[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。  
  
    1.  BizTalk マッパーは、BizTalk プロジェクトに追加します。 BizTalk プロジェクトを右クリックし、[**追加**、] をクリック**新しい項目の**します。  
  
         [新しい項目の追加] ダイアログ ボックスの左側のペインで選択**マップ ファイル**です。 右側のウィンドウから次のように選択します。**マップ**です。 など、マップの名前を指定**ResponseMap.btm**です。 **[追加]** をクリックします。  
  
    2.  送信元スキーマ ペインで、をクリックして**ソース スキーマを開く**です。  
  
    3.  **BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**、WCF ベースの応答メッセージのスキーマを選択して[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。 このチュートリアルでは、次のように選択します。 *Siebel_BussComp_Migration.SiebelDBBindingSchema*です。 **[OK]** をクリックします。  
  
    4.  **送信元スキーマのルート ノード**ダイアログ ボックスで、 *InsertResponse*  をクリック**OK**です。  
  
    5.  送信先スキーマ ペインで、をクリックして**送信先スキーマを開く**です。  
  
    6.  **BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**、vPrev Siebel アダプターの応答メッセージのスキーマを選択します。 このチュートリアルでは、次のように選択します。 *Siebel_BussComp_Migration.AccountService_Account_x5d*です。 **[OK]** をクリックします。  
  
    7.  **ターゲット スキーマのルート ノード**ダイアログ ボックスで、 *InsertResponse*  をクリック**OK**です。  
  
    8.  マップ、 **: 文字列の配列**送信元スキーマ内の要素、**公開: 文字列**に次の図に示すように、送信先スキーマ内の要素。  
  
         ![アダプター バージョン間の応答メッセージをマップ](../../adapters-and-accelerators/adapter-siebel/media/6352035b-79c0-4850-a8f7-e4f6581c8532.gif "6352035b-79c0-4850-a8f7-e4f6581c8532")  
  
    9. マップを保存します。  
  
5.  保存し、BizTalk ソリューションをビルドします。 ソリューションを右クリックし、をクリックして**ソリューションのビルド**です。  
  
6.  ソリューションを展開する。 ソリューションを右クリックし、をクリックして**ソリューションの配置**です。  
  
## <a name="next-steps"></a>次の手順  
 Wcf-custom 送信ポートを作成および構成」の説明に従って、この手順で作成したマップを使用するように[手順 2: Oracle データベース アダプターを使用する BizTalk Server 管理コンソールでオーケストレーションを構成する](../../adapters-and-accelerators/adapter-oracle-database/step-2-configure-an-orchestration-to-use-the-oracle-db-adapter-in-biztalk.md)です。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 2: Siebel の BizTalk プロジェクトを移行します。](../../adapters-and-accelerators/adapter-siebel/tutorial-2-migrating-biztalk-projects-in-siebel.md)