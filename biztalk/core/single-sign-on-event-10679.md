---
title: "シングル サインオン: イベント 10679 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 645f2b74-2cbe-4c6a-b0f5-7e31f93f88c6
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f612f3cf6540340124a3f11ed99fe736df65296b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10679"></a>シングル サインオン: イベント 10679
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10679|  
|イベント ソース|ENTSSO|  
|コンポーネント|N\A|  
|シンボル名|SSO_WARN_PS_MAPPING_DISABLED|  
|メッセージ テキスト|外部パスワードが変更されています。 マッピングが無効になっているため、外部アカウントのパスワードは変更されませんでした。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: %2 %r<br /><br /> アプリケーション名: %3 %r<br /><br /> 外部アカウント: %4|  
  
## <a name="explanation"></a>説明  
 この警告イベントは、マッピングが無効になっているため、外部アカウントのパスワードが変更されなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 この警告を解消するには、次の手順を実行します。  
  
-   SSO 管理ツールを使用して、このアダプターのマッピングを有効にします。  
  
## <a name="more-info"></a>詳細
  
-   [パスワード同期](../core/password-synchronization2.md)  
  
-   **パスワード同期アダプターのプロパティ: オプション**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]