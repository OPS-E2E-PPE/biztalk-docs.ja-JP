---
title: 'シングル サインオン: イベント 10558 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 84637b67-09df-4c1e-b9f2-85a738ba0d7a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c2ee5c21bdf90e6aedcdbe2ac83e0e51a7f48f6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270802"
---
# <a name="single-sign-on-event-10558"></a>シングル サインオン: イベント 10558
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10558|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|SSO_WARN_USER_OWN_MAPPINGS|  
|メッセージ テキスト|アプリケーション ユーザーは各自のマッピングを制御することのみ許可されています。%r<br /><br /> ドメイン名: %1 %r<br /><br /> ユーザー名: %2 %r<br /><br /> アプリケーション名: %3 %r<br /><br /> クライアント ユーザー: %4|  
  
## <a name="explanation"></a>説明  
 アプリケーション ユーザーが他のユーザーのマッピングを制御しようとしました。 これは許可されていません。  
  
## <a name="user-action"></a>ユーザーの操作  
 マッピングを制御できるのは、その特定のマッピングのアプリケーション ユーザーだけです。