---
title: シングル サインオン:イベント 10747 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63ae1ab4-0f4e-45a7-83c1-31b8037e4dd7
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2dd430869a49a7ec6085f29f4ef5403b99a6540
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395516"
---
# <a name="single-sign-on-event-10747"></a>シングル サインオン:イベント 10747
## <a name="details"></a>詳細  

|                 |                                                                                                                                        |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                       エンタープライズ シングル サインオン                                                        |
| 製品バージョン |                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                       |
|    イベント ID     |                                                                 10747                                                                  |
|  イベント ソース   |                                                                  該当なし                                                                   |
|    コンポーネント    |                                                                  該当なし                                                                   |
|  シンボル名  |                                                     SSO_ERROR_UNKNOWN_NOTIFICATION                                                     |
|  メッセージ テキスト   | 不明な通知の種類を受信しました。 received.%r<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: % 2 %r<br /><br /> 通知の種類: %3 |

## <a name="explanation"></a>説明  
 このエラー イベントは、SSO サービスによって、無効な通知の種類で内部エラーが検出されたことを示します。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  

- 関連するイベントのシステムおよびアプリケーション イベント ログを確認します。  

  詳細については、次のリソースを参照してください。  

- [SSO の使用](../core/using-sso.md)
