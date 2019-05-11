---
title: アセンブリと例外管理サンプルがインストールされているアイテム |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af580992-73d4-4b16-a1cc-fa819b441fca
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac0a14eeb6eaca71cf346c901b33b03f590ca563
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392287"
---
# <a name="assemblies-and-artifacts-installed-by-the-exception-management-samples"></a>アセンブリとアイテム例外管理サンプルによりインストール
次の表は、アセンブリと、ESB 例外管理サンプルのインストールされている他の成果物を示します。  
  
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
|%Program Files %\\BizTalk Server\Pipeline コンポーネント|パイプライン コンポーネント||