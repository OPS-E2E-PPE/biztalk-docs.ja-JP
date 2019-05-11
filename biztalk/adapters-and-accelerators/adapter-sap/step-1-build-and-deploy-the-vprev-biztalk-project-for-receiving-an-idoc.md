---
title: 手順 1:ビルドおよび IDOC を受信するための vPrev BizTalk プロジェクトの配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migration, building and deploying previous version of BizTalk project for receiving an IDOC
- migrating, building and deploying previous version of BizTalk project for receiving an IDOC
- migration
ms.assetid: ab6bdf9a-dca5-4acd-97b2-a9afe9792978
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ff4cd20f579c41b3bcba504c527e20ae6ba3314
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372852"
---
# <a name="step-1-build-and-deploy-the-vprev-biztalk-project-for-receiving-an-idoc"></a>手順 1:ビルドおよび IDOC を受信するための vPrev BizTalk プロジェクトの配置
![ステップ 1/3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")  
  
 **所要時間:** 5 分  
  
 **目標:** この手順では、ビルドし、SAP システムから IDOC を受信する既存の vPrev BizTalk プロジェクトをデプロイします。  
  
> [!NOTE]
>  VPrev BizTalk プロジェクトに何も変更する必要はありません。  
  
## <a name="prerequisites"></a>前提条件  
 SAP システムから ORDERS03 IDOC を受信する vPrev BizTalk プロジェクトが必要です。  
  
### <a name="to-build-and-deploy-the-vprev-biztalk-project"></a>ビルドおよび vPrev BizTalk プロジェクトを配置するには  
  
1.  構築して、ソリューションをデプロイするために必要な厳密な名前キー ファイルを作成します。 厳密な名前キー ファイルを作成するには、次の操作を行います。  
  
    1.  Visual Studio コマンド プロンプトを起動します。  
  
    2.  コマンド プロンプトでは、キー ファイルを作成するフォルダーに移動します。 たとえば、「 **cd C:\Sample**し、ENTER キーを押します。  
  
    3.  コマンド プロンプトで「 **sn-k\<キー ファイル名\>.snk**し、ENTER キーを押します。  
  
2.  ソリューション エクスプ ローラーで、BizTalk ソリューション名を右クリックし、をクリックし、**プロパティ**します。 **プロパティ ページ** ダイアログ ボックスで、次の操作を行います。  
  
    1.  をクリックして**構成プロパティ**チェック ボックスを左側のウィンドウと必ずから、**ビルド**と**デプロイ**列を選択します。  
  
    2.  **[OK]** をクリックします。  
  
3.  ソリューション エクスプ ローラーで BizTalk プロジェクトを右クリックし、をクリックし、**プロパティ**します。 **プロパティ ページ** ダイアログ ボックスで、次の操作を行います。  
  
    1.  左側のウィンドウで展開**共通プロパティ**アセンブリを順にクリックします。  
  
    2.  右側のウィンドウで 、**厳密な名前**カテゴリの**アセンブリ キー ファイル**プロパティ、先ほど作成したアセンブリ キー ファイルへのパスを指定します。  
  
    3.  **[OK]** をクリックします。  
  
4.  ソリューション エクスプ ローラーでソリューション名を右クリックし をクリックし、**ソリューションのビルド**します。  
  
5.  ソリューションが正常にビルドできたら、ソリューション名を右クリックし、**ソリューションの配置**します。  
  
## <a name="next-steps"></a>次の手順  
 作成および構成 Wcf-custom の受信ポートと WCF ベースを使用して SAP システムから Idoc を受信するように構成[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]」の説明に従って、[手順 2。Wcf-custom 一方向の構成の受信ポート](../../adapters-and-accelerators/adapter-sap/step-2-configure-a-wcf-custom-one-way-receive-port.md)します。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 4: SAP の IDOC 受信 BizTalk プロジェクトを移行する](../../adapters-and-accelerators/adapter-sap/tutorial-4-migrating-an-sap-receive-idoc-biztalk-project.md)