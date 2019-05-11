---
title: 例外処理の Web サービス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dfe6ebdf-9b92-40c7-93fb-afd6c5f68aaa
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 924a8262c3ebe474f79c2c169f3fd58ed5e9e4fe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399732"
---
# <a name="the-exception-handling-web-service"></a>例外処理の Web サービス
例外処理の Web サービスは、エラー メッセージを受け取り、ESB 例外ポータルに公開します。 クライアント アプリケーションでは、例外メッセージを作成でき、その例外の種類、またはジェネリック ハンドラーでは、構成されている任意のハンドラーが例外を処理できる、ESB に送信することができます。 このサービスの主な利点は、ESB ESB 例外処理機構に参加するアプリケーションの外部エンティティができることです。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このサービスの 2 つのバージョンが含まれています。 ASP.NET (ASMX) バージョンと Windows Communication Foundation (WCF) のバージョン。 サービス名は**ESB します。ExceptionHandlingServices**と**ESB します。ExceptionHandlingServices.WCF**、それぞれ、およびサービスが 1 つのメソッドを公開します。  
  
- **SubmitFault**します。 このメソッドは、のインスタンスを受け取り、 **FaultMessage**クラス、戻り値はありません。  
  
  例外処理メカニズムの動作方法については、次を参照してください。 [ESB 例外管理を使用して](../esb-toolkit/using-esb-exception-management.md)します。  
  
> [!NOTE]
>  既定では、例外処理の Web サービスはセキュリティで保護の Sockets Layer (SSL) クライアントがアクセスするときに要求するように構成されていません。 クライアント アクセス用の SSL が要求されるように、サービスを構成し、インターネット インフォメーション サービス (IIS) Web サービスのホスト コンピューターとをホストするサーバー間の接続を保護する必要があります、 **ESBExceptions**データベースネットワーク レベルの IPSec と適切なファイル レベルのアクセス制御リスト (ACL) アクセス許可を使用します。