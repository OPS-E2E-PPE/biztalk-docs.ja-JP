---
title: 'シングル サインオン: イベント 10747 |Microsoft Docs'
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
ms.openlocfilehash: a6303d7dd39c2168d67d206401bdf8d2c30f5d21
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993915"
---
# <a name="single-sign-on-event-10747"></a>シングル サインオン: イベント 10747
## <a name="details"></a>詳細  

|                 |                                                                                                                                        |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                       エンタープライズ シングル サインオン                                                        |
| 製品バージョン |                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                       |
|    イベント ID     |                                                                 10747                                                                  |
|  イベント ソース   |                                                                  N\A                                                                   |
|    コンポーネント    |                                                                  N\A                                                                   |
|  シンボル名  |                                                     SSO_ERROR_UNKNOWN_NOTIFICATION                                                     |
|  メッセージ テキスト   | 不明な通知の種類が受信されました。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: % 2 %r<br /><br /> 通知の種類: %3 |

## <a name="explanation"></a>説明  
 このエラー イベントは、無効な通知の種類に関する内部エラーが SSO サービスによって検出されたことを示します。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  

- システムおよびアプリケーションのイベント ログで関連するイベントを確認します。  

  詳細については、次のリソースを参照してください。  

- [SSO の使用](../core/using-sso.md)
