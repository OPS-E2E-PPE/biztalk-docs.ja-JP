---
title: 'パターンと設計: サービス指向ソリューション |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- patterns [service solutions], examples
- examples, programming patterns
- patterns [service solutions], designing
- designing, programming patterns
ms.assetid: c196cd9d-2b2d-4548-bc7d-26196f7c2878
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0663a9ec82a1e50807f676f7e46211d433086bff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351591"
---
# <a name="designing-with-patterns-the-service-oriented-solution"></a>パターンと設計: サービス指向ソリューション
サービス指向ソリューションでは、他のアプリケーションで使用するためのサービスとしての BizTalk アプリケーションを公開する方法を示します。 サービスとしてアプリケーションを表示すると、他のアプリケーションを簡単に情報を使用し、提供されているサービスで使用できます。 詳細については、サービスはインターフェイスを参照してください「Service Interface」 [ http://go.microsoft.com/fwlink/?LinkId=46185](http://go.microsoft.com/fwlink/?LinkId=46185)します。 サービス指向の統合の詳細についてはの「Service-Oriented Integration」を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=46186](http://go.microsoft.com/fwlink/?LinkId=46186)します。  
  
 ソリューションは、その他の 3 つのアプリケーションからの関連情報を集約した後に Web サービスの応答として情報を提供するクレジット情報アプリケーションです。 アプリケーションでは、結果を統合し、まとめられたクレジット情報を含む 1 つのメッセージを返します。 次の 3 つのバックエンド システムは次のとおりです。  
  
- **SAP Enterprise システム:** SAP バックエンドは、顧客の全体的な与信限度を提供します。 ソリューションで SAP アダプターを使用してこのバックエンド システムと通信[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。  
  
- **Pending Transactions システム。** Pending Transactions システムは、アカウントの未処理トランザクションの合計量を報告します。 ソリューションでは、Windows Server からメインフレームとの通信に Microsoft Host Integration Server (HIS) を使用します。 また、彼のトランザクション インテグレータ技術も使用します。 これらは、Web サービスとしてのメインフレームと対話するシステムを有効にします。 BizTalk オーケストレーションでは、この Web サービスを使用します。  
  
- **Payment Tracking システム。** Payment Tracking システムは、個別に行われた最後の支払いを報告します。 このシステムでは、MQSeries を使用します。  
  
  ソリューションの概要から、前述したように、MQSeries キューを Web サービス以外のインターフェイスも使用できます。 (アプリケーションの一般的な構造の詳細については、次を参照してください。[サービス指向ソリューションを理解する](../core/understanding-the-service-oriented-solution.md))。 Web サービスには、サービス指向アーキテクチャを構築する最も一般的な方法が、すべてのアプリケーションはそれらを使用できます。 BizTalk Server ソリューションを提供できますが、Web サービス、従来のアプリケーション サービスを使用するための代替手段とします。  
  
  MQSeries アクセスは、レガシ音声自動応答システムがソリューションを使用する方法をシミュレートします。 MQSeries アクセスは、Web サービス アクセスとは、1 つのソリューションを使用して、レガシ アプリケーションと新しいアプリケーションの両方で方法を示します。  
  
## <a name="patterns-used-in-the-service-oriented-solution"></a>サービスで使用されるパターン指向のソリューション  
 次の図は、サービス指向ソリューションでパターンの簡略化されたバージョンを示します。  
  
 ![サービス&#45;ソリューション パターンを指向](../core/media/service-oriented-solution-patterns.gif "Service_Oriented_Solution_Patterns")  
  
 ソリューションは、パターンを表す 4 つの主要な部分で構成されています。 サービス インターフェイス、コンテンツ ベースのルーター、受信者一覧、およびアグリゲーター。 サービス インターフェイスは、ソリューションに接続できるようにするインターフェイス メカニズムを表します。 コンテンツ ベースのルーターはメッセージの有効性をチェックしが有効でない場合は、エラー メッセージを送信します。 受信者の一覧は、次の 3 つのバックエンド アプリケーションに、メッセージを送信します。 バックエンド アプリケーションの応答として、アグリゲーターは 1 つの応答メッセージに応答を結合します。 応答メッセージは、サービス インターフェイスを要求元に戻ります。  
  
 ダイアグラムで指定されていない場合は、多くの左注:  
  
-   図では、メッセージ トランスレータは、外部システムと通信するために、ソリューションに必要なを省略します。  
  
-   図では、バックエンド プロセスと通信する方法を指定されていません。  
  
-   また、図では、サービス インターフェイスの性質は指定しません。  
  
-   示されて同期または非同期の通信を使用するかどうか。  
  
## <a name="see-also"></a>参照  
 [開発、サービス指向ソリューション](../core/developing-a-service-oriented-solution.md)   
 [指向ソリューションのサービスのパターンの変換](../core/translating-the-patterns-of-the-service-oriented-solution.md)