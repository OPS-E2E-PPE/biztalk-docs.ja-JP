---
title: "シングル サインオン: イベント 10809 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7331d12b-1000-4a60-83b3-f092968e0e51
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e010c6ee391e72ec270ddbdc767bed861836cb8f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10809"></a>シングル サインオン: イベント 10809
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10809|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|ENTSSO_E_HISSO_APP_NOT_ENABLED|  
|メッセージ テキスト|アプリケーションはホスト側開始シングル サインオンに対して有効になっていません。|  
  
## <a name="explanation"></a>説明  
 アプリケーションはホスト側開始シングル サインオンに対して有効になっていません。  
  
## <a name="user-action"></a>ユーザーの操作  
 管理ツールを使用して、ホスト側開始シングル サインオンを構成します。 次の設定を行います  
  
 アプリケーションの SSO_FLAG_SSO_EXTERNAL_TO_WINDOWS フラグが設定されます。