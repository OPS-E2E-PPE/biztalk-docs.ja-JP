---
title: 'シングル サインオン: イベント 11036 |Microsoft Docs'
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
ms.openlocfilehash: f19a3ff1d35d3c2de04ec9c3846de94d7a2657a7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013915"
---
# <a name="single-sign-on-event-11036"></a>シングル サインオン: イベント 11036
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                                                                エンタープライズ シングル サインオン                                                                                                                                                                |
| 製品バージョン |                                                                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                |
|    イベント ID     |                                                                                                                                                                          11036                                                                                                                                                                          |
|  イベント ソース   |                                                                                                                                                                         ENTSSO                                                                                                                                                                          |
|    コンポーネント    |                                                                                                                                                                           なし                                                                                                                                                                           |
|  シンボル名  |                                                                                                                                                         SSO_INFO_PS_WIN_CHANGE_ADAPTER_NO_SYNC                                                                                                                                                          |
|  メッセージ テキスト   | Windows パスワードが変更されています。 この Windows アカウントのマッピングが見つかりましたが、このアプリケーションについて、アダプターは外部システムとのパスワード同期をサポートしないように構成されているので無視されました。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> Windows アカウント: % 2 %r<br /><br /> アプリケーションの場合: % 3 %r<br /><br /> アダプター: % 4 %r<br /><br /> クライアント ユーザー: %5 |
  
## <a name="explanation"></a>説明  
 この Windows アカウントのマッピングが見つかりましたが、このアプリケーションについて、アダプターは外部システムとのパスワード同期をサポートしないように構成されているので無視されました。  
  
## <a name="user-action"></a>ユーザーの操作  
 アダプターの構成を確認します。  
  
 パスワード同期については、[パスワード同期](../core/password-synchronization2.md)を参照してください。