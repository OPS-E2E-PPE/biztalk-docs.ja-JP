---
title: 手順 3:テスト、Solution2 |Microsoft Docs
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
ms.openlocfilehash: 9e585019df8d6aa13374bb5648d37b10273d99cd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392638"
---
# <a name="step-3-test-the-solution"></a>手順 3:ソリューションをテストします。
![ステップ 3/3](../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")  
  
 **所要時間:** 5 分  
  
 **目標:** この手順では、EAI ソリューションでのメッセージの処理方法をテストします。  
  
 **目的:** この手順では、EAIProcess オーケストレーションがメッセージを正しく処理することを確認します。 EAI アプリケーションに指定された受信場所にサンプル メッセージを削除しています。 これを行います。 500 個を超える項目、倉庫から EAIProcess オーケストレーションがメッセージを受信する場合、EAI ソリューションは、適切に動作は、オーケストレーションは、要求拒否メッセージを生成します。 では、EAIProcess オーケストレーションでは、500 未満の項目を要求するウェアハウスからメッセージを受信した場合、オーケストレーションは、メッセージを ERP システムを渡します。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を開始する前に行う必要があります[手順 2。構成し、アプリケーションを起動](../core/step-2-configure-and-start-the-application1.md)します。  
  
## <a name="procedures"></a>手順  
  
#### <a name="to-test-the-eai-solution"></a>EAI ソリューションをテストするには  
  
1.  Windows エクスプ ローラーを開きに移動します**C:\BTSTutorials\WareHouse**します。  このフォルダーは、チュートリアル ファイルをインストールすることによって作成されます。  
  
2.  コピー **RequestInstance.XML**貼り付けます**C:\BTSTutorials\WareHouse\Request**します。  
  
3.  ファイルが、確認**C:\BTSTutorials\ERP\Request**します。  
  
4.  Windows エクスプ ローラーに移動します。 **C:\BTSTutorials\WareHouse**します。  
  
5.  コピー **RequestInstance (上限) を超えています。XML**貼り付けます**C:\BTSTutorials\WareHouse\Request**します。  
  
6.  ファイルが、確認**C:\BTSTutorials\WareHouse\RequestDecline**します。  
  
## <a name="what-did-i-just-do"></a>でしただけ何か。  
 EAI アプリケーションの受信場所にサンプル メッセージを配置することで、EAI ソリューションをテストします。  
  
## <a name="see-also"></a>参照  
 [ステップ 1: プロジェクトを配置します。](../core/step-1-deploy-the-projects.md)   
 [手順 2:アプリケーションの構成と開始](../core/step-2-configure-and-start-the-application1.md)