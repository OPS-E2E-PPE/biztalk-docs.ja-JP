---
title: "変換の Web サービス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 788bf4a9-a63b-4fd3-93a2-6e34a1464049
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5abad7a5a7bae3c76fba58ecd92fc3384df5ca25
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-transformation-web-service"></a>変換の Web サービス
変換の Web サービスでは、外部アプリケーションを ESB アプリケーションにドキュメントを送信し、展開された Microsoft BizTalk マップを使用して変換を使用します。 変換エージェントとは異なり、このサービスは、BizTalk メッセージ ボックス データベースを経由してメッセージをルーティングされません。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このサービスの 2 つのバージョンが含まれています: ASP.NET (ASMX) バージョンと Windows Communication Foundation (WCF) バージョン。 サービス名は**ESB です。TransformServices**と**ESB です。TransformServices.WCF**、それぞれ、およびサービスが 1 つのメソッドを公開します。  
  
-   **変換します。** このメソッドは、パラメーターとして、**文字列**を変換するメッセージを格納していると、**文字列**BizTalk に展開されているマップの完全修飾名を格納しています。 このメソッドを返します、**文字列**変換されたドキュメントを格納しています。 文字列パラメーターの使用は、異機種混在環境での相互運用性のリスクを軽減します。ただし、これによって、Web サービス (biztalk 変換サービスがより適してサイズの大きいドキュメント) 大きなドキュメントの変換に使用しないように注意してください。  
  
> [!NOTE]
>  既定では、変換の Web サービスは (SSL) クライアントによってアクセスされたときに要求するように構成されていません。 クライアント アクセス用の SSL が要求されるようにサービスを構成し、インターネット インフォメーション サービス (IIS) Web サービスのホスト コンピューターとネットワーク レベルの IPSec および適切なファイル レベルのアクセスを使用して、BizTalk Server 間の接続を保護する必要があります。リスト (ACL) のアクセス許可を制御します。