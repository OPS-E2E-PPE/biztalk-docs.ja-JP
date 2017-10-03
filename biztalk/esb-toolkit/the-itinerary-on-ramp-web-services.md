---
title: "道順のランプで Web サービス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d7551974-b9d2-4ae3-b54c-3aa5ba058e95
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36d3724a6cd57dca8157c05e95d9e196f0fb6cf8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-itinerary-on-ramp-web-services"></a>道順のランプで Web サービス
行程 Web サービスが、itinerary 入り口行程サービスによって、Microsoft BizTalk ターゲットにし、それ以降の処理または ESB 操作のためのメッセージを送信するクライアントできるようにするメソッドを公開します。  
  
 行程 Web サービスに渡しますペイロード ESB 行程パイプライン コンポーネントでこれらのサービスが定義されていることを確認する旅程を検証する、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]構成します。 コンポーネントは、検証済みの日程を含むメッセージに特殊なコンテキスト プロパティを追加します。  
  
 場合は、ジェネリック itinerary 入り口、日程を含む SOAP ヘッダーはメッセージの送信中に指定されていません。 したがって、ESB 行程セレクター パイプライン コンポーネントは、ESB 行程パイプライン コンポーネントの代わりに使用されます。 ESB 行程セレクター パイプライン コンポーネントは、定義済みの競合回避モジュールの接続文字列に基づく旅程を解決し、ESB 行程パイプライン コンポーネントを提供する同じ検証を提供します。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]一方向の両方をサポートする行程サービスおよび要求-応答メッセージ交換パターンの 2 つのバリエーションが含まれています。 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ASP.NET (ASMX) および Windows Communication Foundation (WCF) のバージョンのこれらのサービスの両方を含むジェネリックのバージョンの WCF サービスを提供します。  
  
 指定された一方向の itinerary サービスの名前は**ESB です。ItineraryService**、 **ESB です。ItineraryServices.WCF**、および**ESB です。ItineraryServices.Generic.WCF**です。  
  
 提供されている双方向 itinerary サービスの名前は**ESB です。ItineraryServices.Response**、 **ESB です。ItineraryServices.Response.WCF**、および**ESB です。ItineraryServices.Generic.Response.WCF**です。  
  
 各行程 Web サービスには、次の方法によって公開されます。  
  
-   **SubmitRequest**です。 このメソッドは、ASMX ベースのサービスのインスタンスを受け取り、 **XmlNode**を送信するメッセージを含むクラスです。 WCF に基づくサービスの場合は、このメソッドは、送信するメッセージを含む XML 文字列を受け取ります。  
  
-   **SubmitRequestResponse**です。 このメソッドは、ASMX ベースのサービスのインスタンスへの参照を受け取ります、 **XmlNode**クラスで送信するメッセージを含みのインスタンスの応答メッセージが返されます、 **XmlNode**に渡されるです。 このメソッドは、WCF ベースのサービスへの参照を受け取ります、**オブジェクト**XML 文字列を送信するメッセージを含むの配列を返しますとなる型**XmlNodes**で、**オブジェクト**に渡されました。  
  
 行程 Web サービスの使用の詳細については、次を参照してください。[のインストールと旅程ランプでサンプルを実行して](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)です。  
  
> [!NOTE]
>  既定では、行程 Web サービスは (SSL) クライアントによってアクセスされたときに要求するように構成されていません。 クライアント アクセス用の SSL を要求して、インターネット インフォメーション サービス (IIS) Web サービスのホスト コンピューターとネットワーク レベルの IPSec を使用して、ESBExceptions データベースをホストするサーバー間の接続を保護し、適切なサービスを構成する必要があります。ファイル レベルのアクセス制御リスト (ACL) のアクセス許可。