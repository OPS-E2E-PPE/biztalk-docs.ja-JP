---
title: BizTalk メッセージ ボックス データベースに永続化せず変換 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7f5b4caf-88e9-41dd-a644-e229e411a4a7
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 407725509121948619e4eb05b583f6c8c1362f9f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294986"
---
# <a name="transformation-without-persisting-to-the-biztalk-message-box-database"></a>BizTalk メッセージ ボックス データベースに永続化せず変換
このユース ケースで Web サービスへの呼び出しが適用するには、適切なマップの実行時の解像度に基づいて、メッセージのリアルタイムの変換を実行し、変換後の結果を返します。 図 1 は、プロセスの概略を示します。  
  
 ![永続化せず変換](../esb-toolkit/media/ch3-transformationwithout.gif "Ch3 TransformationWithout")  
  
 **図 1**  
  
 **Microsoft BizTalk Server メッセージ ボックス データベースに保存することがなく、メッセージを変換します。**  
  
 含まれる変換サービスのサンプル、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示しています。 使用すると、ESB 変換サービスを呼び出すことができます。これにより、コンポーネントと、BizTalk Server ビジネス ルール エンジンのポリシーを開発しているように、変換とマッピングをテストすることができます。  
  
 詳細については、次を参照してください。[をインストールすると、変換サービスのサンプルを実行している](../esb-toolkit/installing-and-running-the-transformation-service-sample.md)です。  
  
> [!NOTE]
>  ここでは、BizTalk Server の変換エージェントによって実行される動的変換操作で参照変換のサービスを混同しないでください。 変換サービスは、高パフォーマンス Web サービスを BizTalk Server を直接呼び出すことによって、メッセージ ボックス データベースを通過せずに待機時間を大幅に短縮します。