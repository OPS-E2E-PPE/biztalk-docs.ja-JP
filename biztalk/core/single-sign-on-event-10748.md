---
title: シングル サインオン:イベント 10748 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6b4b18ea-6565-4c0b-89f8-30a8c67601ba
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 518f12cbf89b345775c6e486d522ca1e667d9142
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395484"
---
# <a name="single-sign-on-event-10748"></a>シングル サインオン:イベント 10748
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                              エンタープライズ シングル サインオン                                                                                              |
| 製品バージョン |                                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                              |
|    イベント ID     |                                                                                                        10748                                                                                                        |
|  イベント ソース   |                                                                                                       ENTSSO                                                                                                        |
|    コンポーネント    |                                                                                                         該当なし                                                                                                         |
|  シンボル名  |                                                                                           SSO_WARN_PS_ADAPTER_NOT_RUNNING                                                                                           |
|  メッセージ テキスト   | 変換先アダプターに接続できませんでした。<br /><br /> 実行中または initialized.%r はなりません。<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: % 2 %r<br /><br /> SSO サーバー名: % 3 %r<br /><br /> エラー コード: %4 |

## <a name="explanation"></a>説明  
 この警告イベントは、パスワード同期が、指定したパスワード同期アダプターに接続できなかったことを示します。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の 1 つ以上の操作を行います。  

- 外部アダプターを確認します。  

- アダプターを有効にするのにには、MMC スナップインまたはコマンド ライン ツールを使用します。  

- 関連付けられているエラーのシステムおよびアプリケーション イベント ログを確認します。  

  詳細については、次のリソースを参照してください。  

- [パスワード同期を管理する方法](../core/how-to-administer-password-synchronization.md)
