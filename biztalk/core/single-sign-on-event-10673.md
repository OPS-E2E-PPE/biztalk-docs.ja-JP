---
title: 'シングル サインオン: イベント 10673 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fa1d572a-1e9f-496e-a219-852e7d9228d5
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8068d7ec43cc07dfd76b21dc749ca062226e49f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271394"
---
# <a name="single-sign-on-event-10673"></a>シングル サインオン: イベント 10673
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10673|  
|イベント ソース|ENTSSO|  
|コンポーネント|N\A|  
|シンボル名|SSO_INFO_WINDOWS_MAPPING_CONFLICT_ALLOWED|  
|メッセージ テキスト|外部パスワード変更により、複数の Windows アカウントが変更されます。%r<br /><br /> この外部システムのアダプターは、マッピングの競合を許可するように構成されているため、これは許可されます。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: %2 %r<br /><br /> 外部アカウント: %3 %r<br /><br /> Windows アカウント 1: %4 %r<br /><br /> Windows アカウント 2: %5|  
  
## <a name="explanation"></a>説明  
 この情報イベントは、外部パスワード変更により複数の Windows アカウントが変更されることを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
  
-   ユーザーの操作は必要ありません。  
  
## <a name="more-info"></a>詳細
  
-   [パスワード同期を管理する方法](../core/how-to-administer-password-synchronization.md)  
  
-   **パスワード同期アダプターのプロパティ: オプション**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
  
-   [パスワード同期](../core/password-synchronization2.md)