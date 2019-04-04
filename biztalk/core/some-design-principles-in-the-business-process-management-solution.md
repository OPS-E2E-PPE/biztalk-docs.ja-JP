---
title: 一部のデザインの原則には、ビジネス プロセス管理ソリューションで |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business processes, design principals
- designing, design principals
- process management solution tutorial, dividing business processes
- patterns [process management solutions], design principals
ms.assetid: 688b970f-8e64-4a47-bcc5-bdb9c5195902
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7c7a6b614e9836f9536c6446a209a83aa764f29
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970043"
---
# <a name="some-design-principles-in-the-business-process-management-solution"></a>ビジネス プロセス管理ソリューションにおけるいくつかの設計方針
ここでは、まず、ビジネス プロセスをステージに分割する一般的なガイドラインを説明します。 次に、これらのガイドラインとビジネス要件に関連するソリューションのオーケストレーション、アセンブリ、およびアプリケーションのいくつかについて、その構造を検討します。 ビジネス要件の詳細については、の「ビジネス要件」を参照してください[、ビジネス プロセス管理ソリューションを理解する](../core/understanding-the-business-process-management-solution.md)します。  
  
## <a name="dividing-business-processes"></a>ビジネス プロセスの分割  
 ビジネス プロセスを検討する場合、多くは、最初にビジネス プロセスを単一の大きなプロセスとして扱います。 これは、必ずしも最適な設計ではありません。 Southridge Video の注文は、長時間実行されるビジネス プロセス (完了までに 1 年かかる) です。 その間、ビジネス プロセス自体が変更される可能性があります。 インプロセスの注文を中断しないでビジネス プロセスを更新するため、Southridge Video の注文処理はステージに分割されます。  
  
 プロセスをどこで分割するかは、プロセスのどの部分をバージョン管理するか、および未処理の注文に対して許可する中断の種類を決定する重要な要素です。 Southridge Video ソリューションは、4 つの一般的な基準を使用して、ステージを決定します。  
  
- ビジネス プロセスのステップの論理的なグループ。  
  
- オーケストレーション内の操作の範囲。  
  
- ビジネス プロセスを考慮した場合のバージョン管理に便利なプロセスの要素。  
  
- オーケストレーションは、長時間を要する操作を実行した後に終了する。  
  
  4 つのうち、1 番目と 3 番目が最も重要です。これは、論理的なグループやバージョン管理が自明な要素よりも操作の範囲が通常かなり広くなるためです。 ただし、範囲の途中でオーケストレーションを終了する必要はないので注意してください。  
  
  最初のステージでは、オーケストレーションを見る場合**CableOrder1.odx**要求-応答シーケンスが、facilities system を効果的に終了すると表示されます。 これは、注文を実行する実際の処理を含むプロセスの一部なので、ステージが終了する場所として適しています。 オーケストレーションの最後付近に長時間実行されるステップを用意する場合、復元するとオーケストレーションがすぐに終了します。 これにより、新しいバージョンのオーケストレーションへのソリューション全体の移動速度が上がります。  
  
> [!NOTE]
>  ソリューションでプロセスが不連続のステージに分割されますが、ソリューションを監視すると、BAM を通じて連続ビューで表示できます。  
  
## <a name="order-action-broker-and-manager-orchestrations"></a>Order Action、Broker、および Manager オーケストレーション  
 注文処理ステージに分割する、以外もわかります各注文のアクション: たとえば、注文、注文の検証を分析するには、注文の取り消し-個別のオーケストレーションでは。 各アクションを個別のオーケストレーションに配置すると、ステージの構造からアクションが分離されます。 これにより、注文処理ステージのデザインおよびバージョン管理の柔軟性が向上します。  
  
 注文ブローカと注文マネージャは、ほとんど同じ理由で個別のオーケストレーションに格納されます。 ソリューションのデザインでは、他の種類の注文を処理するため、複数の注文マネージャを使用できます。 ブローカとマネージャを分離する場合も、異なる場所でこれらを格納できます。 注文ブローカのデザインの詳細については、次を参照してください"なぜ注文ブローカとでしょうか。"。 [OrderBroker オーケストレーションで処理](../core/processing-in-the-orderbroker-orchestration.md)します。 注文マネージャの詳細については、[プロセス マネージャのロジック](../core/process-manager-logic.md)を参照してください。  
  
## <a name="assemblies"></a>アセンブリ  
 ソリューションのアセンブリは、コンポーネントのバージョン管理や他のサーバーへのコンポーネントの移動をサポートするためにまとめられています。 たとえば、スキーマは、個別のアセンブリに格納されています。 特に、注文ブローカのスキーマは、独自のアセンブリに格納されます。 これにより、ソリューションの他の要素を変更しないで、バージョンを管理できます。 また、注文ブローカを個別のグループまたはサーバーに移動することが簡単になります。 アプリケーションのバージョン管理とスキーマ アセンブリの詳細については、[ビジネス プロセス管理ソリューションのバージョン管理](../core/versioning-the-business-process-management-solution.md)を参照してください。  
  
## <a name="applications"></a>[アプリケーション]  
 BizTalk 管理コンソールで確認する場合、作成されたソリューションは 3 つの独立したアプリケーションで構成されていることがわかります。  
  
- **BTSScn.BPM.OrderBrokerApp**、注文ブローカを含むアプリケーション  
  
- **BTSScn.BPM.CableOrderApp**、注文処理コンポーネントが含まれるアプリケーション  
  
- **BTSScn.BPM.MessagingApp**、他の 2 つのアプリケーションで共有アイテムを収集するアプリケーション  
  
  同じ BizTalk グループ内で他のアプリケーションのアイテムを使用する BizTalk アプリケーションの機能によって、ソリューションを 3 つの部分で構成できます。 別のアプリケーションのアイテムを使用するには、参照しているアプリケーションから他のアプリケーションに参照を追加します。 他のアプリケーションを参照する方法の詳細については、[別のアプリケーションへの参照を追加する方法](../core/how-to-add-a-reference-to-another-application.md)を参照してください。  
  
  個別のアプリケーションに一般的なアイテムを配置すると、1 つの場所だけでコンポーネントを更新できることがあります。 共有されるコンポーネントは、ポートを含めて、任意に指定できます。 たとえば、ソリューションのオーケストレーションは、エラーをエラー報告ポートに送信します。 このポートは、メッセージング アプリケーション BTSScn.BPM.MessagingApp にあり、ソリューション全体でこのポートを使用できます。  
  
  また、3 つのアプリケーションとしてソリューションを構造化すると、ソリューションの一部を他のサーバーに簡単に移動できます。 各アプリケーションと参照されているアプリケーションを MSI ファイルに変換し、 別のコンピュータにその MSI ファイルをインストールします。 アプリケーションを MSI ファイルに変換する方法の詳細については、[BizTalk アプリケーションのエクスポート方法](../core/how-to-export-a-biztalk-application.md)を参照してください。  
  
### <a name="the-test-solution"></a>テスト ソリューション  
 BizTalk 管理コンソールにも次の 3 つのテスト アプリケーション: **BTSScn.BPM.OrderBrokerApp.Test**、 **BTSScn.BPM.CableOrderApp.Test**、および**BTSScn.BPM.MessagingApp.Test**します。 これらの 3 つのアプリケーションは、テスト アプリケーションに使用するポートだけを格納し、メイン アプリケーションによって参照されます。 この構造は、メイン アプリケーションによって使用されるテスト ポートを考慮して、ソリューションからテスト ポートを分離すると同時に、テスト ソリューションを構築します。  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューションの実装の要点](../core/implementation-highlights-of-the-business-process-management-solution.md)   
 [ビジネス プロセス管理ソリューションのパターン](../core/patterns-in-the-business-process-management-solution.md)