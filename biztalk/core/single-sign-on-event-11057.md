---
title: "シングル サインオン: イベント 11057 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e165e24-fe43-4899-ab6e-1437f639f534
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ca69661d1421433c44472e0572c5d4d4bf76a13
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11057"></a>シングル サインオン: イベント 11057
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|11057|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|SSO_WARN_PS_DIRECT_MISSING_INITIAL_CREDS|  
|メッセージ テキスト|直接パスワード変更。 このマッピングで不足する外部資格情報フィールドの一部は既定値に設定されています。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> アプリケーション名: %2 %r<br /><br /> Windows アカウント: %3 %r<br /><br /> 外部アカウント: %4|  
  
## <a name="explanation"></a>説明  
 直接パスワード同期を使用してパスワードを変更できますが、この機能は外部資格情報フィールドを 1 つだけサポートしています。 この場合、ENTSSO システムで複数の外部資格情報フィールドが検出されたため、これらのフィールドは既定 (空白) 値に設定されました。  
  
## <a name="user-action"></a>ユーザーの操作  
 ユーザーの操作は必要ありません。