---
title: 手順 3 (Azure 用):Service Bus キューの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7192c3c-4ebf-49c4-b8ce-46a6e9fb5f4a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7fe6744ab7f12b539efb9a91627abe9111373e4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392614"
---
# <a name="step-3-for-azure-create-a-service-bus-queue"></a>手順 3 (Azure 用):Service Bus キューを作成します。
このトピックでは、Service Bus のキューを後に販売注文が送信される X12 が処理され、EDI アグリーメントを使用して変換を作成します。  
  
### <a name="to-create-a-service-bus-queue"></a>Service Bus キューを作成するには  
  
1.  ログイン、 [Windows Azure CTP 管理ポータル](http://go.microsoft.com/fwlink/p/?LinkId=202886)Microsoft アカウントを使用します。  
  
2.  ページの下部左側にある、次のようにクリックします。 **AppFabric**します。  
  
3.  左側のツリーでサービスを展開し、サブスクリプションを展開する必要がありますが既に作成した名前空間をクリックします。 場合は、名前空間をまだ持っていないを参照してください。[方法。作成または変更を Windows Azure CTP サービス Namespace](http://msdn.microsoft.com/library/windowsazure/hh697699.aspx)します。  
  
4.  キューのクリックを作成する**新しいキュー**から、**エンティティの管理**ページの上部にあるツールバーのカテゴリ。  
  
5.  **新しいキュー**  ダイアログ ボックスで、キューの名前を入力します。 このチュートリアルと名前を入力します。 `queueordersedi`、 をクリックし、 **OK**します。 作成した EDI アグリーメントの一部としてこの名前を指定した[手順 2 (Azure 用)。EDI アグリーメントを作成](../core/step-2-for-azure-create-an-edi-agreement.md)です。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 4: BizTalk Server 2013 を使用してハイブリッド アプリケーションを作成します。](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)