---
title: "手順 1: 構築して、IDOC を送信するため vPrev BizTalk プロジェクトを配置 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- migration, building and deploying previous version of BizTalk project for sending an IDOC
- migration
ms.assetid: 1982b318-45d1-464e-b7e4-65d459c439e3
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b9089e90fc3a429d6d594a18b0e1fb6e94d4f72
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-build-and-deploy-the-vprev-biztalk-project-for-sending-an-idoc"></a>手順 1: 構築して、IDOC を送信するため vPrev BizTalk プロジェクトを配置
![手順 1/3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")  
  
 **所要時間:** 5 分  
  
 **目標:**このステップでビルドして、IDOC を SAP システムに送信する既存 vPrev BizTalk プロジェクトを展開します。  
  
> [!NOTE]
>  VPrev BizTalk プロジェクトに変更する必要はありません。  
  
## <a name="prerequisites"></a>前提条件  
 BOMDOC IDOC を SAP システムに送信する vPrev BizTalk プロジェクトが必要です。  
  
### <a name="to-build-and-deploy-the-vprev-biztalk-project"></a>ビルドして vPrev BizTalk プロジェクトを配置するには  
  
1.  ビルドし、ソリューションの配置に必要な厳密な名前キー ファイルを作成します。 厳密な名前キー ファイルを作成するには、次の操作を行います。  
  
    1.  Visual Studio コマンド プロンプトを起動します。  
  
    2.  コマンド プロンプトで、キー ファイルを作成するフォルダーに移動します。 たとえば、入力**cd C:\Sample**、ENTER キーを押します。  
  
    3.  コマンド プロンプトで次のように入力します。 **sn-k\<キー ファイルの名前 > .snk**、ENTER キーを押します。  
  
2.  ソリューション エクスプ ローラーで、BizTalk ソリューション名を右クリックし、をクリックして**プロパティ**です。 **プロパティ ページ** ダイアログ ボックスで、次の操作します。  
  
    1.  左側のペインでは、構成プロパティ をクリックしにあるチェック ボックスを確認してください、**ビルド**と**展開**列を選択します。  
  
    2.  **[OK]**をクリックします。  
  
3.  ソリューション エクスプ ローラーで、BizTalk プロジェクトを右クリックし、をクリックして**プロパティ**です。 **プロパティ ページ** ダイアログ ボックスで、次の操作します。  
  
    1.  左側のウィンドウで展開**共通プロパティ**アセンブリをクリックします。  
  
    2.  右側のペインで下にある、**厳密な名前**カテゴリの**アセンブリ キー ファイル**プロパティ、先ほど作成したアセンブリ キー ファイルへのパスを提供します。  
  
    3.  **[OK]**をクリックします。  
  
4.  ソリューション エクスプ ローラーでソリューション名を右クリックし、をクリックして**ソリューションのビルド**です。  
  
5.  正常にビルドできたら、ソリューション名を右クリックし、をクリックして**ソリューションの配置**です。  
  
## <a name="next-steps"></a>次の手順  
 作成し、Wcf-custom 送信ポートを構成および WCF ベースを使用して SAP システムへの Idoc を送信するように構成[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]」の説明に従って、[手順 2: Wcf-custom 一方向送信ポートを構成する](../../adapters-and-accelerators/adapter-sap/step-2-configure-a-wcf-custom-one-way-send-port.md)です。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 3: SAP 送信 IDOC の BizTalk プロジェクトを移行します。](../../adapters-and-accelerators/adapter-sap/tutorial-3-migrating-an-sap-send-idoc-biztalk-project.md)