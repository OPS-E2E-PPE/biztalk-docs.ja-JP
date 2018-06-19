---
title: SWIFTNet クライアントとサーバー |Microsoft ドキュメント
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
ms.openlocfilehash: 5ea3a1b974a26f90d03bb65675c1c4e8966720f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224658"
---
# <a name="swiftnet-client-and-server"></a>SWIFTNet クライアントとサーバー
SWIFT 条項クライアントとサーバーを使用して送信および受信について説明します。 SWIFT クライアントは、SWIFTNet 経由で通信を開始する SWIFTNet リンク (SNL) を呼び出すプロセスです。 BizTalk Server で、これは、送信アダプターが呼び出されます。 SWIFT サーバーは、SWIFTNet 経由でトラフィックを受信すると、SNL によって呼び出されるプログラムです。 BizTalk Server で、受信アダプターは、呼び出されます。  
  
 SWIFT クライアントとビジネス クライアントとサーバーでサーバーを混同しないでください。 たとえば、クライアント (組織) は、サーバー (組織) によって提供されるサービスに依存します。 サーバー (組織) は、クライアント (組織) との通信を開始する場合、必要があります SNL クライアント アプリケーションのためとを使用して、着信トラフィックを受信する SNL サーバー アプリケーションがクライアント (組織) に必要です。 これは、次の図で説明します。  
  
 ![クライアントとサーバー間の SWIFTNet 関係](../../adapters-and-accelerators/fileact-interact/media/7ad5d877-19d4-431f-9358-d5ae278cf945.gif "7ad5d877-19d4-431f-9358-d5ae278cf945")  
  
 SNL では、クライアントとサーバーの両方のアプリケーションは、コマンド プロンプトから起動された実行可能ファイルを前提としています。 どちらも DLL にリンク SNL API、SNL インスタンスの実際のプロセスと通信します。  
  
## <a name="snl-client-applications"></a>SNL クライアント アプリケーション  
 SNL クライアント アプリケーションは、次に示す SwCall API に依存します。 技術的には、一般的なクライアント アプリケーションできるように記述します。  
  
```  
Main:  
  Initialize SNL API  
  Repeat  
    Call SwCall API  
  Until shutdown  
```  
  
 SNL によるクライアントのコンテキストを参照しているために、アプリケーションが専用のプロセスで実行する必要があります SNL クライアント プロセス id。 SNL は、SwCall タキシード リソースを使用する呼び出しを同期します。 その結果、一度に 1 つのクライアント スレッドだけは、SwCall 効果的に実行できます。  
  
 クライアントでは、同期通信モードをサポートします。 これは、SWCall で戻り値には、応答から返されたとき、サーバーが発生することを意味します。 [次へ] SwCall は、この戻り値の後にのみ実行できます。  
  
## <a name="snl-server-applications"></a>SNL サーバー アプリケーション  
 SNL サーバー アプリケーションは、クライアントのアプリケーションよりも若干複雑です。 サーバー アプリケーションは、SNL DLL にブロッキング呼び出しを実行する前に、コールバック関数を登録します。 技術的には、一般的なサーバー アプリケーションできるように記述します。  
  
```  
Main:  
  Initialize SNL API  
  Call SwRegisterSwCallback, registering the Callback function  
  Call SwServer, block and receive callbacks  
  
Callback(Request):  
  Process Request  
  Return Response  
```  
  
 サーバー アプリケーションは、コールバック関数の中に SwCall API を呼び出すことができます。 場合によっては、目的の結果または応答を生成できる SwCall 呼び出す必要があります。 ただし、サーバー アプリケーションは、ネットワーク経由で通信を開始することができますされません。 サーバー アプリケーションでは、クライアント アプリケーションをすることはできません。  
  
 次の図に、呼び出しというラベルの付いた**初期化**SNL API 初期化プロセスは、複数の呼び出しを必要とする抽象化したものです。 ラベルの付いた呼び出し**SwCallback()** が複数回繰り返す、および呼び出しというラベルの付いた**SwCall()** は省略可能です。  
  
 ![SNL サーバー機能](../../adapters-and-accelerators/fileact-interact/media/42395775-cdbc-4e36-8b36-566caefa2aaf.gif "42395775-cdbc-4e36-8b36-566caefa2aaf")  
  
 サーバーと SNL API DLL の間のすべての呼び出しは、標準の C 呼び出し規約の同期の関数呼び出しです。  
  
## <a name="see-also"></a>参照  
 [FileAct を理解し、アダプターのアーキテクチャの対話](../../adapters-and-accelerators/fileact-interact/understanding-fileact-and-interact-adapter-architecture.md)   
 [SWIFT 送信アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-architecture.md)   
 [SWIFT 受信アダプターのアーキテクチャ](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md)