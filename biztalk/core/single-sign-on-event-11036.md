---
title: 'シングル サインオン: イベント 11036 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2dad0427-83dd-42ac-b0bc-d113abdc8e89
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63b11005248471c222f63c88439a0e60571b341e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277154"
---
# <a name="single-sign-on-event-11036"></a>シングル サインオン: イベント 11036
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|11036|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|SSO_INFO_PS_WIN_CHANGE_ADAPTER_NO_SYNC|  
|メッセージ テキスト|Windows パスワードが変更されています。 この Windows アカウントのマッピングが見つかりましたが、このアプリケーションについて、アダプターは外部システムとのパスワード同期をサポートしないように構成されているので無視されました。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> Windows アカウント: %2 %r<br /><br /> アプリケーション: %3 %r<br /><br /> アダプター: %4 %r<br /><br /> クライアント ユーザー: %5|  
  
## <a name="explanation"></a>説明  
 この Windows アカウントのマッピングが見つかりましたが、このアプリケーションについて、アダプターは外部システムとのパスワード同期をサポートしないように構成されているので無視されました。  
  
## <a name="user-action"></a>ユーザーの操作  
 アダプターの構成を確認します。  
  
 パスワード同期については、次を参照してください。[パスワード同期](../core/password-synchronization2.md)です。