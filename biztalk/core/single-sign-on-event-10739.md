---
title: 'シングル サインオン: イベント 10739 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1039c832-80ff-4cc2-97b4-2671672b6b12
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a08c0b5194b3c6cb2a75966a33d7215fd0b7b499
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969451"
---
# <a name="single-sign-on-event-10739"></a>シングル サインオン: イベント 10739
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                               エンタープライズ シングル サインオン                                                                               |
| 製品バージョン |                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                               |
|    イベント ID     |                                                                                         10739                                                                                         |
|  イベント ソース   |                                                                                        ENTSSO                                                                                         |
|    コンポーネント    |                                                                                          N\A                                                                                          |
|  シンボル名  |                                                                       SSO_WARN_PS_SET_WINDOWS_PASSWORD_ADAPTER                                                                        |
|  メッセージ テキスト   | SSO データベースの Windows パスワードを更新できませんでした。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: % 2 %r<br /><br /> Windows アカウント: %3\\% 4 %r<br /><br /> エラー コード: %5 |

## <a name="explanation"></a>説明  
 この警告イベントは、SSO によって、SSO データベース内の Windows パスワードを更新できなかったことを示します。 警告メッセージには、失敗の考えられるさまざまな原因が示されています。場合によっては、この警告で構成の問題が示されることがあります。また、パスワードの変更中にマッピングが削除された可能性もあります。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の操作を行います:   

- パスワードの変更を再試行します。  

- 再試行も失敗する場合、UI またはコマンド ライン ツールを使用して手動でパスワードを変更します。  

  詳細については、次のリソースを参照してください。  

- [パスワード同期](../core/password-synchronization2.md)
