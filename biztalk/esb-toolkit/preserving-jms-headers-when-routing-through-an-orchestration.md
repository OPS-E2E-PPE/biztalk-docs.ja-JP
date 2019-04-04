---
title: オーケストレーション経由でルーティングするときに、JMS ヘッダーを保持 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d9a59ff3-0cbf-499f-92b2-cf5b808d8b3f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 142bd0d2e5ff86362fe3c3ffa7ef8ec256202708
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979715"
---
# <a name="preserving-jms-headers-when-routing-through-an-orchestration"></a>オーケストレーション経由でルーティングするときに、JMS ヘッダーを保持
このユース ケースでは、コンポーネントがで提供される[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]受信メッセージから Java Message Service (JMS) ヘッダーを抽出し、送信メッセージの再構築します。 JMS メッセージのヘッダー情報保持図 1 に示すようには、オーケストレーション内からヘッダーのコンテキストへのアクセスを示します。  
  
 ![JMS の維持](../esb-toolkit/media/ch3-preservingjms.gif "Ch3 PreservingJMS")  
  
 **図 1**  
  
 **ESB オーケストレーション全体でヘッダー情報を JMS の維持および処理**  
  
 JMS MQRFH2 コンポーネント サンプルに含まれている、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示し、次の 3 つの部分で構成されています。  
  
- 第 1 部は、IBM WebSphere MQ、ESB および BizTalk Server と IBM WebSphere MQ のメッセージが移動完全に忠実なヘッダー情報の保持を示します。  
  
- 第 2 部では、ESB オーケストレーション内のコードを使用して MQRFH2 ヘッダー プロパティにアクセスする方法を示します。 この場合、コードは、送信先のキュー名を指定する JMS ヘッダー プロパティを変更します。  
  
- 第 3 部は、一括読み込みのキューでメッセージを示し、アプリケーションがメッセージの内容の一部として指定された送信先キューにメッセージをルーティングする方法を示しています。  
  
  詳細については、[インストールして、JMS MQRFH2 コンポーネント サンプルを実行する](../esb-toolkit/installing-and-running-the-jms-mqrfh2-component-sample.md)を参照してください。