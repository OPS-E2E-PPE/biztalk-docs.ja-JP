---
title: 'WCF アダプター FAQ: WCF エンドポイント |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ccc94b7d-b8a6-4c24-907e-922fd885b874
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90c59c586f0d7f1d02ad406baec694cf4e22ff24
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974296"
---
# <a name="wcf-adapter-faq-wcf-endpoints"></a>WCF アダプター FAQ: WCF エンドポイント
## <a name="what-are-two-endpoints-options-can-be-created-by-the-biztalk-wcf-service-publishing-wizard"></a>BizTalk WCF サービス公開ウィザードで作成できる 2 つのエンドポイント オプションは何ですか。  
 BizTalk WCF サービス公開ウィザードを実行すると、作成するエンドポイントとして WCF サービス エンドポイントか、WCF メタデータ専用エンドポイント (MEX) を選択できます。  
  
 サービス エンドポイントの場合、実際の Web の場所が作成されて IIS でホストされ、実際の WCF サービスの機能が公開されます。 サービス エンドポイントで使用できるのは分離アダプター (WCF-WsHttp、WCF-BasicHttp、および WCF-CustomIsolated) のみです。 この種類のエンドポイントの機能は、オーケストレーションまたはスキーマによって実装され、WCF サービスとして公開されます。  
  
 メタデータ専用エンドポイントの機能は、BizTalk 受信場所を通じて実装されます。  これには、公開されたオーケストレーションや実際の WCF サービス コードではなく、IIS とインプロセス WCF 受信アダプターが使用されます。 ウィザードでメタデータ専用エンドポイントを生成すると、インプロセス WCF アダプターを使用して公開された受信場所の統合情報を提供できます。これは svcutil.exe を使用して手動で行うよりも簡単です。 svcutil.exe を使用する場合は、サービスのコンシューマーにメタデータを転送して呼び出せるようにする方法を見つける必要があります。  
  
## <a name="why-would-i-use-a-metadata-only-endpoint-in-biztalk-server"></a>BizTalk Server でメタデータ専用エンドポイントを使用するとどのような利点がありますか。  
 メタデータ専用エンドポイントでは、実際の WCF サービスにはサービス実装が存在しません。 機能は BizTalk 受信場所に実装され、サービス エンドポイントが設定された WCF サービスと同様に呼び出されます。 たとえば、2 つのスキーマとマップを使用して、メッセージ内のフィールドを取得してすべて大文字に変換するとします。 この場合、サービスは “ConvertToUpper” としてメタデータで公開されます。 しかし、サービスの機能は、コード内やオーケストレーション経由ではなく受信場所に実装されています。  
  
 WCF エンドポイントは、アドレス、バインド、およびコントラクトで構成されます。 ウィザードでメタデータ専用エンドポイントを作成する場合、既存の受信場所からアドレスとバインドの詳細が取得されます。 コントラクト情報は、BizTalk オーケストレーション内にあるスキーマで定義されますが、ウィザードを使用して手動で作成することもできます。 選択した場合**BizTalk オーケストレーションを WCF サービスとして発行**、メタデータ専用エンドポイントでは、オーケストレーション アセンブリからのメッセージとポートの種類を使用して、コントラクトを定義します。  
  
 選択した場合**スキーマを WCF サービスとして公開**ウィザードでは、既存の入力と出力スキーマのサービスやオペレーション名を指定することによって、サービス定義を定義することができます。 メタデータを公開後に参照できるように、ウィザードにより .svc ファイルと IIS 仮想ディレクトリが作成されます。 BizTalk WCF サービス公開ウィザードの httpGetEnabled 属性された web.config ファイルも作成されます、 \<serviceMetadata\>要素が true に設定します。 これにより、メタデータが公開され、参照可能になります。 そのデータを使用して HTTP 経由での GET 要求を通じてアクセスできる BizTalk 受信場所用にサービス メタデータを公開する場合は、`?wsdl`サービスの URL の末尾にします。  
  
## <a name="are-service-endpoints-hosted-in-iis-and-why"></a>サービス エンドポイントは IIS でホストされますか。それはなぜですか。  
 はい。サービス エンドポイントは次の分離アダプターのいずれかを使用して IIS でホストされます。  
  
-   WCF-WsHttp  
  
-   WCF-BasicHttp  
  
-   WCF-CustomIsolated  
  
 サービス エンドポイントは、その機能を WCF サービスとして直接呼び出すことができる点で、メタデータ専用エンドポイントと異なります。 BizTalk WCF サービス公開ウィザードを使用してサービス エンドポイントを作成すると、指定された BizTalk アプリケーションに新しい受信場所が作成されます。 ここで定義された URI を使用して IIS からオーケストレーションにアクセスできます。  
  
## <a name="when-creating-a-service-endpoint-why-would-i-select-to-publish-schemas-as-a-wcf-service"></a>サービス エンドポイントを作成する場合に [スキーマを WCF サービスとして公開する] を選択すると、どのような利点がありますか。  
 WCF 受信場所が、BizTalk メッセージングのみを使用する BizTalk アプリケーションに含まれる場合は、スキーマを WCF サービスとして公開することを選択します。 つまり、オーケストレーションは使用されず、すべての機能は受信場所および送信ポートから公開されます。 スキーマはコントラクト情報を指定するために公開されます。 この情報はスキーマ アセンブリから取得できます。また、オーケストレーション アセンブリからでも取得できます (ただし、このエンドポイントではオーケストレーションは使用されません)。