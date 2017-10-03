---
title: "JMS ヘッダーを保持し、オーケストレーションでルーティングするときに |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9a59ff3-0cbf-499f-92b2-cf5b808d8b3f
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 362f41919a050b08bdba9c70c7771698ab71ce33
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="preserving-jms-headers-when-routing-through-an-orchestration"></a>オーケストレーションでルーティングするときに、JMS ヘッダーを保持します。
このユース ケースでは、コンポーネントがで提供される[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]Java Message Service (JMS) ヘッダーを受信メッセージから抽出し、し、それらを再構築でメッセージを送信します。 JMS メッセージ ヘッダーの保存図 1 に示すようには、オーケストレーション内からヘッダーのコンテキストへのアクセスを示します。  
  
 ![JMS の維持](../esb-toolkit/media/ch3-preservingjms.gif "Ch3 PreservingJMS")  
  
 **図 1**  
  
 **ESB オーケストレーションおよび処理全体で JMS ヘッダー情報を維持します。**  
  
 含まれている、JMS MQRFH2 コンポーネント サンプル、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示し、次の 3 つの部分で構成されています。  
  
-   第 1 部で ESB と BizTalk Server を使用して IBM WebSphere MQ に戻る、IBM WebSphere MQ からメッセージが移動完全に忠実なヘッダーの保存について説明します。  
  
-   第 2 部では、ESB オーケストレーション内のコードが MQRFH2 ヘッダー プロパティにアクセスする方法について説明します。 この場合、コードでは、送信先のキュー名を指定する JMS ヘッダー プロパティを変更します。  
  
-   パート 3 は、一括読み込みのキューがメッセージを示し、アプリケーションがメッセージの内容の一部として指定された送信先キューにメッセージをルーティングする方法を示しています。  
  
 詳細については、次を参照してください。[をインストールすると、JMS MQRFH2 コンポーネント サンプルを実行している](../esb-toolkit/installing-and-running-the-jms-mqrfh2-component-sample.md)です。