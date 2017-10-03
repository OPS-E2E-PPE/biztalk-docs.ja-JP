---
title: "(Azure) の手順 3: Service Bus キューを作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b7192c3c-4ebf-49c4-b8ce-46a6e9fb5f4a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d55b3222798edb245000cdde8de52565c39758a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-for-azure-create-a-service-bus-queue"></a>(Azure) の手順 3: Service Bus キューを作成します。
このトピックでは、EDI アグリーメントを使用して X12 販売注文が処理および変換された後に X12 販売注文の送信先になる、Service Bus キューを作成します。  
  
### <a name="to-create-a-service-bus-queue"></a>Service Bus キューを作成するには  
  
1.  ログインに、 [Windows Azure CTP 管理ポータル](http://go.microsoft.com/fwlink/p/?LinkId=202886)Microsoft アカウントを使用します。  
  
2.  ページの下部左側にある、をクリックして**AppFabric**です。  
  
3.  左側のツリーでサービスを展開し、サブスクリプションを展開して、作成済みの名前空間をクリックします。 名前空間既にをお持ちでない場合は、次を参照してください。[する方法: を作成または Windows Azure CTP サービスの Namespace を変更](http://msdn.microsoft.com/library/windowsazure/hh697699.aspx)です。  
  
4.  クリックするキューを作成する**新しいキュー**から、**エンティティの管理**ページの上部にあるツールバーからのカテゴリ。  
  
5.  **新しいキュー**  ダイアログ ボックスで、キューの名前を入力します。 このチュートリアルと名前を入力してください。 `queueordersedi`、順にクリック**OK**です。 作成した EDI アグリーメントの一部としてこの名前を指定する[ステップ 2 (Azure 用): EDI アグリーメントを作成する](../core/step-2-for-azure-create-an-edi-agreement.md)です。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 4: BizTalk Server 2013 を使用するハイブリッド アプリケーションを作成します。](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)