---
title: '手順 1: 構築して、IDOC を受信するため vPrev BizTalk プロジェクトを配置 |Microsoft ドキュメント'
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
ms.openlocfilehash: f99971a421530e4901c8bbac6533809a0f2f273c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963328"
---
# <a name="step-1-build-and-deploy-the-vprev-biztalk-project-for-receiving-an-idoc"></a>手順 1: 構築して、IDOC を受信するため vPrev BizTalk プロジェクトを配置
![手順 1/3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")  
  
 **所要時間:** 5 分  
  
 **目標:** このステップでビルドして SAP システムから IDOC を受信する既存 vPrev BizTalk プロジェクトを展開します。  
  
> [!NOTE]
>  VPrev BizTalk プロジェクトに変更する必要はありません。  
  
## <a name="prerequisites"></a>前提条件  
 SAP システムから ORDERS03 IDOC を受信する vPrev BizTalk プロジェクトが必要です。  
  
### <a name="to-build-and-deploy-the-vprev-biztalk-project"></a>ビルドして vPrev BizTalk プロジェクトを配置するには  
  
1.  ビルドし、ソリューションの配置に必要な厳密な名前キー ファイルを作成します。 厳密な名前キー ファイルを作成するには、次の操作を行います。  
  
    1.  Visual Studio コマンド プロンプトを起動します。  
  
    2.  コマンド プロンプトで、キー ファイルを作成するフォルダーに移動します。 たとえば、入力**cd C:\Sample**、ENTER キーを押します。  
  
    3.  コマンド プロンプトで次のように入力します。 **sn-k\<キー ファイルの名前\>.snk**、ENTER キーを押します。  
  
2.  ソリューション エクスプ ローラーで、BizTalk ソリューション名を右クリックし、をクリックして**プロパティ**です。 **プロパティ ページ** ダイアログ ボックスで、次の操作します。  
  
    1.  をクリックして**構成プロパティ**チェック ボックスを確認してください、左側のウィンドウから、**ビルド**と**展開**列を選択します。  
  
    2.  **[OK]** をクリックします。  
  
3.  ソリューション エクスプ ローラーで、BizTalk プロジェクトを右クリックし、をクリックして**プロパティ**です。 **プロパティ ページ** ダイアログ ボックスで、次の操作します。  
  
    1.  左側のウィンドウで展開**共通プロパティ**アセンブリをクリックします。  
  
    2.  右側のペインで下にある、**厳密な名前**カテゴリの**アセンブリ キー ファイル**プロパティ、先ほど作成したアセンブリ キー ファイルへのパスを提供します。  
  
    3.  **[OK]** をクリックします。  
  
4.  ソリューション エクスプ ローラーでソリューション名を右クリックし、をクリックして**ソリューションのビルド**です。  
  
5.  正常にビルドできたら、ソリューション名を右クリックし、をクリックして**ソリューションの配置**です。  
  
## <a name="next-steps"></a>次の手順  
 作成および構成する Wcf-custom 受信ポートと WCF ベースを使用して SAP システムから Idoc を受信するように構成[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]」の説明に従って、[手順 2: Wcf-custom 一方向受信ポートを構成](../../adapters-and-accelerators/adapter-sap/step-2-configure-a-wcf-custom-one-way-receive-port.md)です。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 4: SAP の IDOC 受信 BizTalk プロジェクトを移行する](../../adapters-and-accelerators/adapter-sap/tutorial-4-migrating-an-sap-receive-idoc-biztalk-project.md)