---
title: BizTalk メッセージ ボックス データベースに永続化せず変換 |Microsoft Docs
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
ms.openlocfilehash: 37f0b126a018f497add4b595ffb09d4eca1559a3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399622"
---
# <a name="transformation-without-persisting-to-the-biztalk-message-box-database"></a>BizTalk メッセージ ボックス データベースに永続化せずに変換
このユース ケースで Web サービスへの呼び出しが適用するには、適切なマップの実行時の解像度に基づいて、メッセージのリアルタイムの変換を実行し、変換された結果を返します。 図 1 は、プロセスの概略を示します。  
  
 ![永続化せず変換](../esb-toolkit/media/ch3-transformationwithout.gif "Ch3 TransformationWithout")  
  
 **図 1**  
  
 **Microsoft BizTalk Server メッセージ ボックス データベースに永続化せず、メッセージを変換します。**  
  
 変換サービス サンプルに含まれている、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示します。 使用すると、ESB 変換サービスを呼び出すことができます。これにより、コンポーネントと BizTalk Server ビジネス ルール エンジンでポリシーを開発しているように、変換およびマッピングをテストすることができます。  
  
 詳細については、次を参照してください。[をインストールすると、変換サービス サンプルを実行している](../esb-toolkit/installing-and-running-the-transformation-service-sample.md)します。  
  
> [!NOTE]
>  ここでは、BizTalk Server の変換エージェントによって実行される動的変換操作で参照変換のサービスを混同しないでください。 変換サービスとは、BizTalk Server を直接呼び出すことによって、メッセージ ボックス データベースを経由せずに待機時間を大幅に短縮高性能な Web サービスです。