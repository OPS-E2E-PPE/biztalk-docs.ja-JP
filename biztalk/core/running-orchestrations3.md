---
title: "Orchestrations3 を実行している |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, running
- Receive shape [Orchestration Designer], starting orchestrations
- Start Orchestration shape [Orchestration Designer], starting orchestrations
- Call Orchestration shape [Orchestration Designer], starting orchestrations
- Receive shape [Orchestration Designer], activating orchestrations
ms.assetid: 5bfe61c9-80e0-4a0a-b6b1-ab48037e665e
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 550fc1e03f3583215a817028917000c9a9c3074a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="running-orchestrations"></a>オーケストレーションの実行
オーケストレーション インスタンスに構成されていますか別のオーケストレーションからの明示的な呼び出しによってトリガーされる: を使用して、**オーケストレーションの呼び出し**図形または**オーケストレーションの開始**図形 — の受信時、アクティブ化メッセージ。 アクティベーション メッセージ スキーマが指定された、**メッセージ**プロパティです。 同様に、オーケストレーションをデザインする必要があり、設定するか、 **Activate**プロパティを**受信**true、または呼び出し元のオーケストレーションが存在しを実行する正しく構成されているかどうかを確認する図形、新しいオーケストレーションです。  
  
 インスタンスを実行するためには、まず BizTalk アセンブリをバインドおよび展開し、オーケストレーション エンジンを参加および開始させて処理を開始しておく必要があります。 詳細については、次を参照してください。 [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)と[を管理する BizTalk アプリケーションの展開と](../core/deploying-and-managing-biztalk-applications.md)です。 オーケストレーションが他のオーケストレーションから呼び出されたとき、または、アクティベーション受信の条件と一致するメッセージがエンジンに送信されると、エンジンによって新しいオーケストレーション インスタンスが作成され、実行されます。 エンジンは、複数の異なるインスタンスを同時に実行することができます。  
  
## <a name="calling-and-starting-orchestrations"></a>オーケストレーションの呼び出しと開始  
 **オーケストレーションの呼び出し**図形と**オーケストレーションの開始**図形は、別のオーケストレーションをアクティブ化を使用することができます。 いずれの場合も、呼び出し元は、パラメーターを渡すことによって他のオーケストレーションと情報を交換できます。 詳細については、次を参照してください。[オーケストレーションにパラメーターを追加する方法](../core/how-to-add-parameters-to-orchestrations.md)です。  
  
## <a name="using-activation-receives-with-filter-expression"></a>フィルター式を指定したアクティベーション受信の使用  
 **受信**図形は、ライセンス認証のための条件を要求するフィルター式を使用も可能性があります。 適切な型のメッセージがあり、一部のプロパティまたはメッセージのプロパティのすべてのフィルター式で条件を満たす場合、**受信**図形がメッセージを受け入れるし、オーケストレーションがアクティブ化します。 このような受信図形と呼びます、*アクティベーション受信*です。  
  
## <a name="see-also"></a>参照  
 [オーケストレーションの呼び出し図形を構成する方法](../core/how-to-configure-the-call-orchestration-shape.md)   
 [オーケストレーションの開始図形を構成する方法](../core/how-to-configure-the-start-orchestration-shape.md)   
 [受信図形を構成する方法](../core/how-to-configure-the-receive-shape.md)   
 [ビルドとオーケストレーションの実行](../core/building-and-running-orchestrations.md)