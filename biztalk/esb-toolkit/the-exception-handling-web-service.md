---
title: "例外処理の Web サービス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dfe6ebdf-9b92-40c7-93fb-afd6c5f68aaa
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb8d8f3439e3b99d118e2932d0a158113ec51be2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-exception-handling-web-service"></a>例外処理の Web サービス
例外処理 Web サービスは、エラー メッセージを受け入れるし、ESB 例外ポータルに公開します。 クライアント アプリケーションでは、例外メッセージを作成でき、その例外の型またはジェネリック ハンドラー用に構成されたハンドラーが例外を処理できる、ESB に送信することができます。 このサービスの主要な利点は、ESB 例外処理機構に参加する、ESB アプリケーションの外部エンティティできます。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このサービスの 2 つのバージョンが含まれています: ASP.NET (ASMX) バージョンと Windows Communication Foundation (WCF) バージョン。 サービス名は**ESB です。ExceptionHandlingServices**と**ESB です。ExceptionHandlingServices.WCF**、それぞれ、およびサービスが 1 つのメソッドを公開します。  
  
-   **SubmitFault**です。 このメソッドは、のインスタンスを受け取り、 **FaultMessage**クラス、戻り値はありません。  
  
 例外処理機構の動作方法に関する情報を参照してください。 [ESB 例外管理を使用して](../esb-toolkit/using-esb-exception-management.md)です。  
  
> [!NOTE]
>  既定では、例外処理の Web サービスは (SSL) クライアントによってアクセスされたときに要求するように構成されていません。 クライアント アクセス用の SSL が要求されるようにサービスを構成し、インターネット インフォメーション サービス (IIS) Web サービスのホスト コンピューターとをホストするサーバー間の接続を保護する必要があります、 **ESBExceptions**データベースネットワーク レベルの IPSec および適切なファイル レベルのアクセス制御リスト (ACL) のアクセス許可を使用します。