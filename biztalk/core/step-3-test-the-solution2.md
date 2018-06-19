---
title: '手順 3: テストのソリューション 2 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30dbc7c9-3c5f-4953-b26f-5c41141c22ad
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c0e484a9f6af788775ec4ae7309965327378267
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277274"
---
# <a name="step-3-test-the-solution"></a>手順 3: ソリューションをテストします。
![手順 3 3](../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")  
  
 **所要時間:** 5 分  
  
 **目標:** EAI ソリューションでメッセージをどのように処理するかをテストするこの手順でします。  
  
 **目的:** この手順では、EAIProcess オーケストレーションでメッセージが正しく処理されているチェックします。 EAI アプリケーションに指定されている受信場所にサンプル メッセージを格納します。 EAI ソリューションが適切に機能している場合、倉庫から EAIProcess オーケストレーションへのメッセージで要求される項目数が 500 を超えると、オーケストレーションでは要求拒否メッセージが生成されます。 倉庫から EAIProcess オーケストレーションへのメッセージで要求される項目数が 500 以下であれば、メッセージは ERP システムに渡されます。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を開始する前に行う必要があります[手順 2: 構成し、アプリケーションを起動](../core/step-2-configure-and-start-the-application1.md)です。  
  
## <a name="procedures"></a>手順  
  
#### <a name="to-test-the-eai-solution"></a>EAI ソリューションをテストするには、次の操作を行います。  
  
1.  Windows エクスプ ローラーを開きに移動**C:\BTSTutorials\WareHouse**です。  このフォルダーは、チュートリアル ファイルのインストールによって作成されます。  
  
2.  コピー **RequestInstance.XML**貼り付けます**C:\BTSTutorials\WareHouse\Request**です。  
  
3.  ファイルが消え、ときに確認**C:\BTSTutorials\ERP\Request**です。  
  
4.  Windows エクスプ ローラーに移動**C:\BTSTutorials\WareHouse**です。  
  
5.  コピー **RequestInstance (制限) を超えています。XML**貼り付けます**C:\BTSTutorials\WareHouse\Request**です。  
  
6.  ファイルが消え、ときに確認**C:\BTSTutorials\WareHouse\RequestDecline**です。  
  
## <a name="what-did-i-just-do"></a>でしただけは何ですか。  
 このステップでは、サンプル メッセージを EAI アプリケーションの受信場所に格納し、EAI ソリューションをテストしました。  
  
## <a name="see-also"></a>参照  
 [手順 1: 配置プロジェクト](../core/step-1-deploy-the-projects.md)   
 [手順 2: を構成し、アプリケーションを起動](../core/step-2-configure-and-start-the-application1.md)