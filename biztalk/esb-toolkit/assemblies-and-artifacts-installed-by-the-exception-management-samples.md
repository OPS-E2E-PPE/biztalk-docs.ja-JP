---
title: "アセンブリおよび例外管理のサンプルがインストールされているアイテム |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: af580992-73d4-4b16-a1cc-fa819b441fca
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65bcb2681cceb450995b18b7dc00d3d8f5a44d30
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="assemblies-and-artifacts-installed-by-the-exception-management-samples"></a>アセンブリおよび例外管理のサンプルがインストールされているアイテム
次の表には、アセンブリおよび ESB 例外管理サンプル用にインストールされた他のアイテムが一覧表示します。  
  
|場所|カテゴリ|コンポーネントの名前とバージョン|  
|--------------|--------------|---------------------------------------|  
|BizTalk アプリケーション GlobalBank.ESB|オーケストレーション|GlobalBank.ESB.ExceptionHandling.Processes.EAIProcess|  
|||GlobalBank.ESB.ExceptionHandling.Handlers.EAIGenericHandler|  
|||GlobalBank.ESB.ExceptionHandling.Handlers.EAIProcessHandler|  
|BizTalk アプリケーション GlobalBank.ESB|送信ポート|EAIProcessHandler.RepairSubmit|  
|||EAIGenericHandler.PostTmpMsg|  
|||EAIProcess.PostApproval|  
|||EAIProcessHandler.PostDecline|  
|||すべての。Exceptions_FILE (GlobalFaultProcessor パイプラインを参照)|  
|BizTalk アプリケーション GlobalBank.ESB|受信ポート|EAIProcess.RequestPort|  
|BizTalk アプリケーション GlobalBank.ESB|受信場所|EAIProcess.RequestPort_FILE|  
|||EAIProcess.ReSubmit_HTTP|  
|BizTalk アプリケーション GlobalBank.ESB|スキーマ|GlobalBank.ESB.ExceptionHandling.Schemas.System_Properties バージョン 2.0.0.0 以降|  
|||GlobalBank.ESB.ExceptionHandling.Schemas.Request バージョン 2.0.0.0 以降|  
|||GlobalBank.ESB.ExceptionHandling.Schemas.RequestDenied バージョン 2.0.0.0 以降|  
|BizTalk アプリケーション GlobalBank.ESB|パイプライン|GlobalBank.ESB.ExceptionHandling.Pipelines.GlobalFaultProcessor バージョン 2.0.0.0 以降|  
|BizTalk アプリケーション GlobalBank.ESB|リソース|GlobalBank.ESB.ExceptionHandling.Handlers バージョン 2.0.0.0 以降|  
|||GlobalBank.ESB.ExceptionHandling.Processes バージョン 2.0.0.0 以降|  
|||GlobalBank.ESB.ExceptionHandling.Schemas バージョン 2.0.0.0 以降|  
|||GlobalBank.ESB.ExceptionHandling.Pipelines バージョン 2.0.0.0 以降|  
|BizTalk アプリケーション GlobalBank.ESB|ポリシー||  
|BizTalk アプリケーション GlobalBank.ESB|マップ|GlobalBank.ESB.ExceptionHandling.Schemas.MapToReqDenied バージョン 2.0.0.0 以降|  
|グローバル アセンブリ キャッシュ|アセンブリ|GlobalBank.ESB.ExceptionHandling.Handlers バージョン 2.0.0.0 以降|  
|||GlobalBank.ESB.ExceptionHandling.Processes バージョン 2.0.0.0 以降|  
|||GlobalBank.ESB.ExceptionHandling.Schemas バージョン 2.0.0.0 以降|  
|||GlobalBank.ESB.ExceptionHandling.Pipelines バージョン 2.0.0.0 以降|  
|%Program Files %\\[!INCLUDE[prague](../includes/prague-md.md)]\Pipeline コンポーネント|パイプライン コンポーネント||