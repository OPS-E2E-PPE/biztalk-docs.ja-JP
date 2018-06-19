---
title: 'シングル サインオン: イベント 11017 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a4f7264-18aa-4eca-97c9-d5fd7e90e2cc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25ef3f3be84e775fe522b508f7726f3e4e88870b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276778"
---
# <a name="single-sign-on-event-11017"></a>シングル サインオン: イベント 11017
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|11017|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|SSO_PS_WARN_NOT_IN_GROUP_DELETE_OK|  
|メッセージ テキスト|Windows アカウントがアプリケーションのアプリケーション ユーザー アカウントにないため、マッピングは無効です。 マッピングは削除されました。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> Windows アカウント: %2 %r<br /><br /> アプリケーション名: %3 %r<br /><br /> アプリケーション ユーザー: %4|  
  
## <a name="explanation"></a>説明  
 指定された Windows アカウントがアプリケーションのアプリケーション ユーザー アカウントの一部ではなかったか、一時期はそうだったが変更または削除されました。 マッピングは削除されました。  
  
## <a name="user-action"></a>ユーザーの操作  
 システムのパスワード同期アカウント情報を確認するか、情報が有効であることを確認します。 次にマッピングを再作成します。 マッピングの作成ウィザードを使用すると、無効なマッピング情報のリスクが軽減されることに注意してください。