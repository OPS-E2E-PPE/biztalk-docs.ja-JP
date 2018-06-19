---
title: 'シングル サインオン: イベント 11043 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 128d68fb-1905-49b3-9b67-30a9442569cc
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc211e4726c68a16f860dd0431a234765e80b76a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276458"
---
# <a name="single-sign-on-event-11043"></a>シングル サインオン: イベント 11043
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|11043|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|SSO_WARN_PS_ADAPTER_REPORTED_FAILURE|  
|メッセージ テキスト|外部パスワードを変更しようとしたときに、パスワード同期アダプターでエラーが報告されました。 SSO データベース内の外部パスワードは更新されませんでした。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: %2 %r<br /><br /> 外部アカウント: %3 %r<br /><br /> エラー メッセージ: %4 %r<br /><br /> エラー コード: %5|  
  
## <a name="explanation"></a>説明  
 ENTSSO がパスワード変更をパスワード同期アダプターに送信する場合、ENTSSO で SSO データベース内に外部パスワードが作成される前に、外部パスワードを正しく変更しておく必要があります。 この場合、その作業が行われていませんでした。  
  
## <a name="user-action"></a>ユーザーの操作  
 警告メッセージの情報をメモし、システム管理者に問い合わせます。