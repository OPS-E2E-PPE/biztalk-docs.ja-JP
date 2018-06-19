---
title: 'シングル サインオン: イベント 10745 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed630e40-d876-4e90-937e-4d2d54fe9f1a
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fe734562b9d8b3564a08f3f5196d53996bf40ca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270826"
---
# <a name="single-sign-on-event-10745"></a>シングル サインオン: イベント 10745
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10745|  
|イベント ソース|ENTSSO|  
|コンポーネント|N\A|  
|シンボル名|SSO_ERROR_ADAPTER_OFFLINE|  
|メッセージ テキスト|アダプターがオフラインです。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: %2 %r<br /><br /> エラー メッセージ: %3 %r<br /><br /> エラー コード: %4|  
  
## <a name="explanation"></a>説明  
 このエラー イベントは、指定されたアダプターがオフラインであることを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、以下の 1 つ以上の操作を実行します。  
  
-   関連するエラーについては、システムおよびアプリケーションのイベント ログを確認します。  
  
-   外部アダプターでエラーを調べます。  
  
 詳細については、次のリソースを参照してください。  
  
-   [パスワード同期を管理する方法](../core/how-to-administer-password-synchronization.md)