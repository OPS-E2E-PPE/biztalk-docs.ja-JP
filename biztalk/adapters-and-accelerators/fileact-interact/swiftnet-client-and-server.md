---
title: SWIFTNet クライアントおよびサーバー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 89d9f54f-af16-4f14-bbe4-8306758320d8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f18055bfae40f5a2369f153faa811639c1cc51bb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364098"
---
# <a name="swiftnet-client-and-server"></a>SWIFTNet クライアントおよびサーバー
SWIFT では、用語のクライアントとサーバーを使用して、送信と受信について説明します。 SWIFT クライアントは、呼び出す SWIFTNet リンク (SNL) SWIFTNet 経由で通信を開始するプロセスです。 BizTalk Server で、これは、送信アダプターが呼び出されます。 SWIFT サーバーは、SWIFTNet 経由でトラフィックを受信すると、SNL によって呼び出されるプログラムです。 BizTalk Server で、これは受信アダプターは、呼び出されます。  
  
 SWIFT クライアントとビジネス クライアントとサーバーでサーバーを混同しないでください。 たとえば、クライアント (組織) は、サーバー (組織) によって提供されるサービスに依存します。 (組織) のサーバーがクライアント (組織) との通信を開始しようとすると、SNL クライアント アプリケーションを使用して、そのためがあり、着信トラフィックを受信する SNL サーバー アプリケーションがクライアント (組織) に必要です。 これは、次の図で説明します。  
  
 ![クライアントとサーバー間の SWIFTNet 関係](../../adapters-and-accelerators/fileact-interact/media/7ad5d877-19d4-431f-9358-d5ae278cf945.gif "7ad5d877-19d4-431f-9358-d5ae278cf945")  
  
 SNL では、クライアントとサーバーの両方のアプリケーションは、コマンド プロンプトから起動する実行可能ファイルを前提としています。 どちらは、実際の SNL インスタンス プロセスと通信して SNL API DLL にリンクします。  
  
## <a name="snl-client-applications"></a>SNL クライアント アプリケーション  
 SNL クライアント アプリケーションは、以下に示す SwCall API に依存します。 厳密に言うと、典型的なクライアント アプリケーションできますように説明します。  
  
```  
Main:  
  Initialize SNL API  
  Repeat  
    Call SwCall API  
  Until shutdown  
```  
  
 SNL によってクライアント コンテキストを参照しているために、アプリケーションが専用のプロセスで実行する必要があります SNL クライアント プロセス id。 SNL は、タキシード リソース SwCall を使用して呼び出しを同期します。 その結果、一度に 1 つのクライアント スレッドのみは、SwCall 効果的に実行できます。  
  
 クライアントは、同期通信モードをサポートします。 これは、SWCall で戻り値には、サーバーから応答が戻ったときに発生することを意味します。 [次へ] SwCall は、この戻り値の後にのみ実行できます。  
  
## <a name="snl-server-applications"></a>SNL サーバー アプリケーション  
 SNL サーバー アプリケーションは、クライアント アプリケーションより多少複雑です。 サーバー アプリケーションは、SNL DLL にブロッキング呼び出しを実行する前に、コールバック関数を登録します。 厳密に言うと、標準的なサーバー アプリケーションをできるように説明します。  
  
```  
Main:  
  Initialize SNL API  
  Call SwRegisterSwCallback, registering the Callback function  
  Call SwServer, block and receive callbacks  
  
Callback(Request):  
  Process Request  
  Return Response  
```  
  
 サーバー アプリケーションでは、コールバック関数の中に SwCall API を呼び出すことができます。 場合によっては、目的の結果または応答を生成できる SwCall 呼び出す必要があります。 ただし、サーバー アプリケーションは、ネットワーク経由で通信を開始することができますされません。 サーバー アプリケーションでは、クライアント アプリケーションをすることはできません。  
  
 次の図に、呼び出しがというラベルが付いた**初期化**SNL API の初期化プロセスは、複数の呼び出しを必要とする抽象化です。 というラベルの付いた呼び出し**SwCallback()** が何回か繰り返すし、呼び出しというラベルの付いた**SwCall()** は省略可能です。  
  
 ![SNL サーバー機能](../../adapters-and-accelerators/fileact-interact/media/42395775-cdbc-4e36-8b36-566caefa2aaf.gif "42395775-cdbc-4e36-8b36-566caefa2aaf")  
  
 サーバーと SNL API の DLL の間のすべての呼び出しは、標準の C 呼び出し規則の同期の関数呼び出しです。  
  
## <a name="see-also"></a>参照  
 [理解 FileAct および InterAct アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/understanding-fileact-and-interact-adapter-architecture.md)   
 [SWIFT 送信アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-architecture.md)   
 [SWIFT 受信アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md)