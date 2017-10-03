---
title: "シングル サインオン: イベント 11037 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b523ff56-112e-4798-97d2-b1b19e130ec7
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 245b4af07a88c4015048db0ea20fe04b714d0ed4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11037"></a>シングル サインオン: イベント 11037
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|11037|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|SSO_INFO_PS_MAPPING_INVALID|  
|メッセージ テキスト|外部パスワードが変更されています。 マッピングが有効ではなくなっているため、外部アカウントのパスワードは変更されませんでした。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: %2 %r<br /><br /> アプリケーション名: %3 %r<br /><br /> 外部アカウント: %4|  
  
## <a name="explanation"></a>説明  
 マッピングがアプリケーション ユーザー グループに含まれなくなっています。  
  
## <a name="user-action"></a>ユーザーの操作  
 このメッセージには、外部アカウントとアプリケーションの名前が示されます。 この情報を使用して、マッピングが有効ではなくなった理由を調べます。