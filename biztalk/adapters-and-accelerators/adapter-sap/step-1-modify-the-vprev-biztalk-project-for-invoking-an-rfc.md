---
title: 手順 1:RFC を呼び出すための vPrev BizTalk プロジェクトの変更 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migration, modifying previous version of BizTalk project for invoking an RFC
- migration
ms.assetid: 2d4a6cd7-d216-4e0f-8f82-41e044cd325b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a9000f4754517223fe39856cdac9e50e2ab676c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372934"
---
# <a name="step-1-modify-the-vprev-biztalk-project-for-invoking-an-rfc"></a>手順 1:RFC を呼び出すための vPrev BizTalk プロジェクトの変更します。
![ステップ 1/3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")  
  
 **所要時間:** 10 分  
  
 **目標:** この手順では、既存の vPrev BizTalk プロジェクトに、次の変更を行います。  
  
- WCF ベースを使用して、SD_RFC_CUSTOMER_GET RFC のメタデータを生成[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
- WCF ベースを使用して、RFC を呼び出すための要求メッセージに vPrev SAP アダプターを使用して、RFC を呼び出すための要求メッセージにマップ[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
- WCF ベースを使用して受信応答メッセージにマップ[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]vPrev SAP アダプターの応答メッセージにします。  
  
## <a name="prerequisite"></a>前提条件  
  
-   SAP システムで SD_RFC_CUSTOMER_GET RFC を呼び出すための vPrev BizTalk プロジェクトが必要です。  
  
### <a name="to-modify-the-vprev-biztalk-project"></a>VPrev BizTalk プロジェクトを変更するには  
  
1. WCF ベースを使用して、SD_RFC_CUSTOMER_GET RFC のメタデータを生成[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。 使用することができます、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]メタデータを生成します。  
  
    Rfc のメタデータを生成する方法の詳細については、次を参照してください。[参照、SAP で RFC 操作のメタデータを検索し、get](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md)します。 スキーマを生成すると後のような名前のファイル*SapBindingSchema.xsd* BizTalk プロジェクトに追加されます。 このファイルには、WCF ベースを使用して SD_RFC_CUSTOMER_GET を呼び出すためのスキーマが含まれています。[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
2. SD_RFC_CUSTOMER_GET RFC のメタデータを生成すると、ポートのバインド ファイルも作成します。 次の手順で、SAP システムにメッセージを送信する Wcf-custom 送信ポートを作成するこのバインド ファイルが使用されます。 操作の SOAP アクションは、メタデータの生成対象の操作にも設定されます。 SD_RFC_CUSTOMER_GET RFC のメタデータを生成する場合など、送信ポートでの SOAP アクションの操作名では、"SD_RFC_CUSTOMER_GET"になります。 ただし、操作名とオーケストレーションの一部異なる可能性があります、たとえば、作成した論理送信ポートで"Operation_1"。 その結果、送信ポートを使用して SAP システムにメッセージを送信するときに、エラーが発生します。 これを回避するには、ことを確認しますで論理送信ポート、オーケストレーションでは、メタデータを生成する操作名と同じ操作名。  
  
    そのため、このチュートリアルでは、場合 SD_RFC_CUSTOMER_GET RFC のメタデータを生成するための名前を変更"SD_RFC_CUSTOMER_GET"する論理送信ポートの操作。  
  
3. 要求メッセージは、WCF ベースを使用して生成されたスキーマに vPrev SAP アダプターを使用して生成されたスキーマをマップ[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
   1. BizTalk マッパーは、BizTalk プロジェクトに追加します。 BizTalk プロジェクトを右クリックし、[**追加**、] をクリックし、**新しい項目の**します。  
  
       **新しい項目の追加**ダイアログ ボックスで、左側のウィンドウから**マップ ファイル**します。 右側のウィンドウから次のように選択します。**マップ**します。 マップの名前を指定します。 **RequestMap.btm**します。 **[追加]** をクリックします。  
  
   2. 送信元スキーマ ペインで、次のようにクリックします。**ソース スキーマを開く**します。  
  
   3. **BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**、vPrev SAP アダプターの要求メッセージのスキーマを選択します。 このチュートリアルでは、次のように選択します。 *SAP_Migration.SD_RFC_CUSTOMER_GET__x32003*、 をクリックし、 **OK**します。  
  
   4. **送信元スキーマのルート ノード**ダイアログ ボックスで、 *SD_RFC_CUSTOMER_GET_Request*、順にクリックします**OK**します。  
  
   5. 送信先スキーマ ペインで、次のようにクリックします。**送信先スキーマを開く**します。  
  
   6. **BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**、WCF ベースの要求メッセージのスキーマを選択して[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。 このチュートリアルでは、次のように選択します。 *SAP_Migration.SapBindingSchema*、[ok] をクリックします。  
  
   7. **ターゲット スキーマのルート ノード**ダイアログ ボックスで、 *SD_RFC_CUSTOMER_GET*、順にクリックします**OK**します。  
  
       次の図に示すように、両方のスキーマでは、それぞれの要素をマップします。 文字列左スペース削除 functoid を使用して CUSTOMER_T 要素をマップします。 、**ツールボックス**、ドラッグ、**文字列左スペース削除**functoid し、マッパーのグリッドにドロップします。 接続、 **CUSTOMER_T** functoid への送信元スキーマ内の要素。 同様に、接続、 **CUSTOMER_T**を functoid に送信先スキーマ内の要素。 次の図は、functoid を使用して 2 つの要素をマップする方法を示しています。  
  
       ![アダプター バージョン間の要求メッセージをマップ](../../adapters-and-accelerators/adapter-sap/media/f12f280d-766f-4647-bced-435354206fb9.gif "f12f280d-766f-4647-bced-435354206fb9")  
  
      > [!NOTE]
      >  文字列左スペース削除 functoid の詳細についてを参照してください"文字列左トリミング Functoid" [ http://go.microsoft.com/fwlink/?LinkId=105774](http://go.microsoft.com/fwlink/?LinkId=105774)します。  
  
   8. マップを保存します。  
  
4. 応答メッセージは、WCF ベースを使用して生成されたスキーマに vPrev SAP アダプターを使用して生成されたスキーマをマップ[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
   1. BizTalk マッパーは、BizTalk プロジェクトに追加します。 BizTalk プロジェクトを右クリックし、[**追加**、] をクリック**新しい項目の**します。  
  
       **新しい項目の追加**ダイアログ ボックスで、左側のウィンドウから**マップ ファイル**します。 右側のウィンドウから次のように選択します。**マップ**します。 マップの名前を指定します。 **ResponseMap.btm**します。 **[追加]** をクリックします。  
  
   2. 送信元スキーマ ペインで、次のようにクリックします。**ソース スキーマを開く**します。  
  
   3. **BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**、WCF ベースの応答メッセージのスキーマを選択して[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。 このチュートリアルでは、次のように選択します。 *SAP_Migration.SapBindingSchema*、 をクリックし、 **OK**します。  
  
   4. **送信元スキーマのルート ノード**ダイアログ ボックスで、 *SD_RFC_CUSTOMER_GETResponse*、順にクリックします**OK**します。  
  
   5. 送信先スキーマ ペインで、次のようにクリックします。**送信先スキーマを開く**します。  
  
   6. **BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**、vPrev SAP アダプターの応答メッセージのスキーマを選択します。 このチュートリアルでは、次のように選択します。 *SAP_Migration.SD_RFC_CUSTOMER_GET__x32003*、 をクリックし、 **OK**します。  
  
   7. **ターゲット スキーマのルート ノード**ダイアログ ボックスで、 *SD_RFC_CUSTOMER_GET_Response*、順にクリックします**OK**します。  
  
   8. 次の図に示すように、両方のスキーマでは、それぞれの要素をマップします。  
  
       ![アダプター バージョン間の応答メッセージをマップ](../../adapters-and-accelerators/adapter-sap/media/d8dddaba-d978-4159-bcc6-6a6bfee36564.gif "d8dddaba-d978-4159-bcc6-6a6bfee36564")  
  
   9. マップを保存します。  
  
5. 保存し、BizTalk ソリューションをビルドします。 クリックして、ソリューションを右クリックして**ソリューションのビルド**します。  
  
6. ソリューションを展開する。 クリックして、ソリューションを右クリックして**ソリューションの配置**します。  
  
## <a name="next-steps"></a>次の手順  
 Wcf-custom 送信ポートを作成および構成」の説明に従って、この手順で作成したマップを使用するように[手順 2。BizTalk Server 管理コンソールでオーケストレーションを構成](../../adapters-and-accelerators/adapter-sap/step-2-configure-the-orchestration-in-biztalk-server-administration-console1.md)します。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 2: SAP の RFC BizTalk プロジェクトを移行する](../../adapters-and-accelerators/adapter-sap/tutorial-2-migrating-an-sap-rfc-biztalk-project.md)