---
title: Orchestrations3 を実行している |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, running
- Receive shape [Orchestration Designer], starting orchestrations
- Start Orchestration shape [Orchestration Designer], starting orchestrations
- Call Orchestration shape [Orchestration Designer], starting orchestrations
- Receive shape [Orchestration Designer], activating orchestrations
ms.assetid: 5bfe61c9-80e0-4a0a-b6b1-ab48037e665e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc582889d30922b4446e9a941906064a8c08c418
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254540"
---
# <a name="running-orchestrations"></a>オーケストレーションの実行
オーケストレーション インスタンスがデザインされていますか別のオーケストレーションからの明示的な呼び出しによってトリガーされる: を使用して、**オーケストレーションの呼び出し**図形または**オーケストレーションの開始**図形などの受信時に自動的、アクティベーション メッセージ。 アクティベーション メッセージ スキーマが指定された、**メッセージ**プロパティ。 したがって、オーケストレーションを設計する必要があり、いずれかを設定、**アクティブ化**プロパティを**受信**図形を [true]、または呼び出し元のオーケストレーションが存在しが実行を正しく構成されているかどうかを確認します新しいオーケストレーションです。  
  
 インスタンスを実行すると、前にまずバインドし、BizTalk アセンブリを展開しし、参加して処理を開始するオーケストレーション エンジンを起動します。 詳細については、次を参照してください。 [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)と[Deploying and Managing BizTalk Applications](../core/deploying-and-managing-biztalk-applications.md)します。 オーケストレーションが別のオーケストレーションから呼び出され、アクティブ化の条件に一致するエンジンにメッセージが表示されます、受信、エンジンがオーケストレーションの新しいインスタンスを作成し、そのインスタンスを実行します。 多数の異なるインスタンスで同時に実行できます。  
  
## <a name="calling-and-starting-orchestrations"></a>呼び出しとオーケストレーションの開始  
 **オーケストレーションの呼び出し**図形と**オーケストレーションの開始**を別のオーケストレーションをアクティブ化図形を使用することができます。 どちらの場合も、呼び出し元は、他のオーケストレーションと情報を交換するパラメーターに渡すことができます。 詳細については、次を参照してください。[オーケストレーションにパラメーターを追加する方法](../core/how-to-add-parameters-to-orchestrations.md)します。  
  
## <a name="using-activation-receives-with-filter-expression"></a>フィルター式を持つ受信ライセンス認証の使用  
 **受信**図形がアクティブ化の条件をフィルター式を使用も可能性があります。 適切な種類のメッセージがあり、一部のプロパティまたはメッセージのプロパティのすべてのフィルター式で条件を満たす場合、**受信**図形がメッセージを受け入れるし、オーケストレーションがアクティブ化します。 このような受信図形と呼びます、*アクティベーション受信*します。  
  
## <a name="see-also"></a>参照  
 [オーケストレーションの呼び出し図形を構成する方法](../core/how-to-configure-the-call-orchestration-shape.md)   
 [オーケストレーションの開始図形を構成する方法](../core/how-to-configure-the-start-orchestration-shape.md)   
 [受信図形を構成する方法](../core/how-to-configure-the-receive-shape.md)   
 [オーケストレーションのビルドおよび実行](../core/building-and-running-orchestrations.md)