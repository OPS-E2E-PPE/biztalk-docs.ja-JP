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
ms.openlocfilehash: a1bcc8146947f5e3cbaf58e31d1f515a055d102c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974307"
---
# <a name="the-exception-handling-web-service"></a>例外処理の Web サービス
例外処理の Web サービスは、エラー メッセージを受け取り、ESB 例外ポータルに公開します。 クライアント アプリケーションでは、例外メッセージを作成でき、その例外の種類、またはジェネリック ハンドラーでは、構成されている任意のハンドラーが例外を処理できる、ESB に送信することができます。 このサービスの主な利点は、ESB ESB 例外処理機構に参加するアプリケーションの外部エンティティができることです。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このサービスの 2 つのバージョンが含まれています。 ASP.NET (ASMX) バージョンと Windows Communication Foundation (WCF) のバージョン。 サービス名は**ESB します。ExceptionHandlingServices**と**ESB します。ExceptionHandlingServices.WCF**、それぞれ、およびサービスが 1 つのメソッドを公開します。  
  
- **SubmitFault**します。 このメソッドは、のインスタンスを受け取り、 **FaultMessage**クラス、戻り値はありません。  
  
  例外処理メカニズムの動作方法については、[ESB 例外管理を使用して](../esb-toolkit/using-esb-exception-management.md)を参照してください。  
  
> [!NOTE]
>  既定では、例外処理の Web サービスはセキュリティで保護の Sockets Layer (SSL) クライアントがアクセスするときに要求するように構成されていません。 クライアント アクセス用の SSL が要求されるように、サービスを構成し、インターネット インフォメーション サービス (IIS) Web サービスのホスト コンピューターとをホストするサーバー間の接続を保護する必要があります、 **ESBExceptions**データベースネットワーク レベルの IPSec と適切なファイル レベルのアクセス制御リスト (ACL) アクセス許可を使用します。