---
title: '手順 1: RFC を呼び出すため vPrev BizTalk プロジェクトを変更する |Microsoft ドキュメント'
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
ms.openlocfilehash: d1f967a268d8baca3ab12f29bbac4b9eccc3cd75
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218106"
---
# <a name="step-1-modify-the-vprev-biztalk-project-for-invoking-an-rfc"></a>手順 1: RFC を呼び出すため vPrev BizTalk プロジェクトを変更します。
![手順 1/3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")  
  
 **所要時間:** 10 分  
  
 **目標:** このステップで、次を変更する既存の vPrev BizTalk プロジェクト。  
  
-   WCF ベースを使用して SD_RFC_CUSTOMER_GET RFC のメタデータを生成する[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
-   WCF ベースを使用して、RFC を呼び出すための要求メッセージに vPrev SAP アダプターを使用して、RFC を呼び出すための要求メッセージにマップ[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
-   WCF ベースを使用して受信した応答メッセージをマップ[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]vPrev SAP アダプターの応答メッセージにします。  
  
## <a name="prerequisite"></a>前提条件  
  
-   SAP システムで SD_RFC_CUSTOMER_GET RFC を呼び出す vPrev BizTalk プロジェクトが必要です。  
  
### <a name="to-modify-the-vprev-biztalk-project"></a>VPrev BizTalk プロジェクトを変更するには  
  
1.  WCF ベースを使用して SD_RFC_CUSTOMER_GET RFC のメタデータを生成する[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 使用することができます、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]メタデータを生成します。  
  
     Rfc のメタデータを生成する方法については、次を参照してください。[参照、検索と取得操作のメタデータの RFC に SAP](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md)です。 スキーマを生成すると後のような名前のファイルが*SapBindingSchema.xsd*が BizTalk プロジェクトに追加します。 このファイルには、WCF ベースを使用して SD_RFC_CUSTOMER_GET を呼び出すためのスキーマが含まれています。[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
2.  SD_RFC_CUSTOMER_GET RFC のメタデータを生成すると、ポートのバインド ファイルも作成されます。 次の手順で、SAP システムにメッセージを送信する Wcf-custom 送信ポートを作成するこのバインド ファイルが使用されます。 操作の SOAP アクションは、メタデータを生成する操作にも設定されます。 SD_RFC_CUSTOMER_GET RFC のメタデータを生成する場合など、送信ポートでの SOAP アクションで操作名では、"SD_RFC_CUSTOMER_GET"になります。 ただし、操作の名前、オーケストレーションの一部異なる場合があります、たとえばなどを作成する論理送信ポートで"Operation_1"。 結果として、送信ポートを使用して、SAP システムにメッセージを送信するときに、エラーを取得します。 これを防ぐためには、確認の論理送信ポート、オーケストレーションでは、メタデータの生成対象の操作名と同じ操作名。  
  
     そのため、このチュートリアルでは、場合 SD_RFC_CUSTOMER_GET RFC のメタデータを生成するための名前を変更"SD_RFC_CUSTOMER_GET"への論理送信ポート操作します。  
  
3.  要求メッセージの WCF ベースを使用して生成されたスキーマに vPrev SAP アダプターを使用して生成されたスキーマにマップ[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
    1.  BizTalk マッパーは、BizTalk プロジェクトに追加します。 BizTalk プロジェクトを右クリックし、**追加**、クリックして**新しい項目の**します。  
  
         **新しい項目の追加**ダイアログ ボックスで、左ペインで、**マップ ファイル**です。 右側のウィンドウから次のように選択します。**マップ**です。 など、マップの名前を指定**RequestMap.btm**です。 **[追加]** をクリックします。  
  
    2.  送信元スキーマ ペインで、をクリックして**ソース スキーマを開く**です。  
  
    3.  **BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**、vPrev SAP アダプターの要求メッセージのスキーマを選択します。 このチュートリアルでは、次のように選択します。 *SAP_Migration.SD_RFC_CUSTOMER_GET__x32003*、クリックして**OK**です。  
  
    4.  **送信元スキーマのルート ノード**ダイアログ ボックスで、 *SD_RFC_CUSTOMER_GET_Request*、順にクリック**OK**です。  
  
    5.  送信先スキーマ ペインで、をクリックして**送信先スキーマを開く**です。  
  
    6.  **BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**、WCF ベースの要求メッセージのスキーマを選択して[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 このチュートリアルでは、次のように選択します。 *SAP_Migration.SapBindingSchema*、[ok] をクリックします。  
  
    7.  **ターゲット スキーマのルート ノード**ダイアログ ボックスで、 *SD_RFC_CUSTOMER_GET*、順にクリック**OK**です。  
  
         次の図に示すように、両方のスキーマ内の各要素をマップします。 文字列左スペース削除 functoid を使用して CUSTOMER_T 要素をマップします。 そのためから、**ツールボックス**、ドラッグ、**文字列左スペース削除**functoid マッパー グリッドの上にドロップします。 接続、 **CUSTOMER_T** functoid への送信元スキーマ内の要素。 同様に、接続、 **CUSTOMER_T**を functoid に送信先スキーマ内の要素。 次の図は、functoid を使用して 2 つの要素をマップする方法を示しています。  
  
         ![アダプター バージョン間の要求メッセージをマップ](../../adapters-and-accelerators/adapter-sap/media/f12f280d-766f-4647-bced-435354206fb9.gif "f12f280d-766f-4647-bced-435354206fb9")  
  
        > [!NOTE]
        >  文字列左スペース削除 functoid に関する詳細についてを参照してください"文字列左スペース削除 Functoid" [http://go.microsoft.com/fwlink/?LinkId=105774](http://go.microsoft.com/fwlink/?LinkId=105774)です。  
  
    8.  マップを保存します。  
  
4.  応答メッセージは、WCF ベースを使用して生成されたスキーマに vPrev SAP アダプターを使用して生成されたスキーマにマップ[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
    1.  BizTalk マッパーは、BizTalk プロジェクトに追加します。 BizTalk プロジェクトを右クリックし、[**追加**、] をクリック**新しい項目の**します。  
  
         **新しい項目の追加**ダイアログ ボックスで、左ペインで、**マップ ファイル**です。 右側のウィンドウから次のように選択します。**マップ**です。 など、マップの名前を指定**ResponseMap.btm**です。 **[追加]** をクリックします。  
  
    2.  送信元スキーマ ペインで、をクリックして**ソース スキーマを開く**です。  
  
    3.  **BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**、WCF ベースの応答メッセージのスキーマを選択して[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 このチュートリアルでは、次のように選択します。 *SAP_Migration.SapBindingSchema*、クリックして**OK**です。  
  
    4.  **送信元スキーマのルート ノード**ダイアログ ボックスで、 *SD_RFC_CUSTOMER_GETResponse*、順にクリック**OK**です。  
  
    5.  送信先スキーマ ペインで、をクリックして**送信先スキーマを開く**です。  
  
    6.  **BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**、vPrev SAP アダプターの応答メッセージのスキーマを選択します。 このチュートリアルでは、次のように選択します。 *SAP_Migration.SD_RFC_CUSTOMER_GET__x32003*、クリックして**OK**です。  
  
    7.  **ターゲット スキーマのルート ノード**ダイアログ ボックスで、 *SD_RFC_CUSTOMER_GET_Response*、順にクリック**OK**です。  
  
    8.  次の図に示すように、両方のスキーマ内の各要素をマップします。  
  
         ![アダプター バージョン間の応答メッセージをマップ](../../adapters-and-accelerators/adapter-sap/media/d8dddaba-d978-4159-bcc6-6a6bfee36564.gif "d8dddaba-d978-4159-bcc6-6a6bfee36564")  
  
    9. マップを保存します。  
  
5.  保存し、BizTalk ソリューションをビルドします。 ソリューションを右クリックし、をクリックして**ソリューションのビルド**です。  
  
6.  ソリューションを展開する。 ソリューションを右クリックし、をクリックして**ソリューションの配置**です。  
  
## <a name="next-steps"></a>次の手順  
 Wcf-custom 送信ポートを作成し、」の説明に従って、この手順で作成したマップを使用するように構成[手順 2: BizTalk Server 管理コンソールでオーケストレーションを構成する](../../adapters-and-accelerators/adapter-sap/step-2-configure-the-orchestration-in-biztalk-server-administration-console1.md)です。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 2: SAP RFC の BizTalk プロジェクトを移行します。](../../adapters-and-accelerators/adapter-sap/tutorial-2-migrating-an-sap-rfc-biztalk-project.md)