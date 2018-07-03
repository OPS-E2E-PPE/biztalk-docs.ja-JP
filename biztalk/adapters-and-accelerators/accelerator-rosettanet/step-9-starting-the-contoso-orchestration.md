---
title: '手順 9: Contoso オーケストレーションの開始 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, starting orchestrations
ms.assetid: df3ff90b-5a9f-4ae7-819a-11cb36d64ccd
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 994355b67c19a7411c62f8858033e44cb8bdf3f4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990828"
---
# <a name="step-9-starting-the-contoso-orchestration"></a>手順 9: Contoso オーケストレーションの開始
ここでは、物理的な送信元と送信先の場所を定義して、ポートの構成プロセスを実行します。 作成した論理ポートを物理ポートをバインドする[手順 7: ポートの作成と構成](../../adapters-and-accelerators/accelerator-rosettanet/step-7-creating-and-configuring-ports.md)します。 オーケストレーションで実行される物理環境と、オーケストレーションでデザインしたビジネス プロセスを関連付けるにサービスを参加させます。 最後に、Fabrikam とのビジネス トランザクションに参加できるように、オーケストレーションを開始します。  
  
### <a name="to-bind-the-orchestration-ports"></a>オーケストレーション ポートをバインドするには  
  
1.  開いている**BizTalk エクスプ ローラー**します。  
  
2.  BizTalk エクスプ ローラーで、 **BizTalk 構成データベース**、展開**オーケストレーション**、右クリックして **[contosopriceandavailability.privateresponderprocess]**、クリックして**バインド**します。  
  
3.  ポートのバインドのプロパティ ページで、次のように選択します。 **LOB_To_PrivateResponder**で、 **FromLOB**プロパティ。  
  
4.  **ContosoSQLReqResponsePort**ボックスで、 **[3 a2sqlreqresponsesendport]** します。  
  
5.  **ToLOB**プロパティ、展開**送信ポート**選択**PrivateResponder_To_LOB**します。  
  
6.  左側のウィンドウで [構成] ウィンドウで次のように選択します。**ホスト**します。  
  
7.  **ホスト**プロパティで、 **BizTalk ホスト**カテゴリを選択**BizTalkServerApplication**クリックしてドロップダウン リストから**OK**.  
  
### <a name="to-start-the-biztalk-runtime-process"></a>BizTalk ランタイム プロセスを開始するには  
  
1. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]順にクリックします**BizTalk Server 管理**します。  
  
2. BizTalk 管理コンソールの左側のウィンドウで 展開[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**、し、展開**ホスト インスタンス**します。  
  
3. いることを確認の状態、 **BizTalkServerApplication**サービスは**を実行している**します。  
  
### <a name="to-enlist-and-start-the-orchestration"></a>オーケストレーションを登録して開始するには  
  
1.  BizTalk 管理コンソールの左側のウィンドウで展開**アプリケーション**、展開**BizTalk アプリケーション 1**、 をクリックし、**オーケストレーション**します。  
  
2.  右側のウィンドウで右クリックし、 **[contosopriceandavailability.privateresponderprocess]** オーケストレーション、およびクリック**参加**します。  
  
3.  右クリックし、 **[contosopriceandavailability.privateresponderprocess]** オーケストレーション、およびクリック**開始**オーケストレーションを開始します。  
  
## <a name="see-also"></a>参照  
 [Fabrikam ソリューションの作成](../../adapters-and-accelerators/accelerator-rosettanet/creating-the-fabrikam-solution.md)