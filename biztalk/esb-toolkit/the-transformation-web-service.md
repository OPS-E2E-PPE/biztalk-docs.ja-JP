---
title: 変換 Web サービス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 788bf4a9-a63b-4fd3-93a2-6e34a1464049
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5812cd340d2f7e7a47f54e6e77ff39c144542615
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399654"
---
# <a name="the-transformation-web-service"></a>変換 Web サービス
変換 Web サービスには、ESB アプリケーションにドキュメントを送信している展開済みの Microsoft BizTalk マップを使用して変換を外部のアプリケーションができます。 変換エージェントとは異なりこのサービスは、BizTalk メッセージ ボックス データベースを経由してメッセージをルーティングされません。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このサービスの 2 つのバージョンが含まれています。 ASP.NET (ASMX) バージョンと Windows Communication Foundation (WCF) のバージョン。 サービス名は**ESB します。TransformServices**と**ESB します。TransformServices.WCF**、それぞれ、およびサービスが 1 つのメソッドを公開します。  
  
-   **変換します。** このメソッドはパラメーターとして、**文字列**を変換するメッセージを格納していると、**文字列**BizTalk にデプロイされているマップの完全修飾名を格納しています。 メソッドを返します、**文字列**変換されたドキュメントを格納しています。 文字列パラメーターの使用は、異機種混在環境での相互運用性の問題のリスクを軽減します。ただし、(biztalk 変換サービスは、サイズの大きいドキュメントはやりやすくなります)、大きなドキュメントを変換するために使用しないように、Web サービスは、このことに注意してください。  
  
> [!NOTE]
>  既定では、変換の Web サービスはセキュリティで保護の Sockets Layer (SSL) クライアントがアクセスするときに要求するように構成されていません。 クライアント アクセス用の SSL が要求されるように、サービスを構成し、インターネット インフォメーション サービス (IIS) Web サービスのホスト コンピューターとネットワーク レベルの IPSec と適切なファイル レベルのアクセスを使用して、BizTalk Server 間の接続を保護する必要があります。リスト (ACL) のアクセス許可を制御します。