---
title: 'シングル サインオン: イベント 10671 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 06c5564f-6412-4e83-9bec-03264e992ebe
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f321a971f89c535da26604c3e03a2b62ebf060e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000075"
---
# <a name="single-sign-on-event-10671"></a>シングル サインオン: イベント 10671
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                                                                                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                                                                                  エンタープライズ シングル サインオン                                                                                                                                                                                  |
| 製品バージョン |                                                                                                                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                                  |
|    イベント ID     |                                                                                                                                                                                            10671                                                                                                                                                                                            |
|  イベント ソース   |                                                                                                                                                                                           ENTSSO                                                                                                                                                                                            |
|    コンポーネント    |                                                                                                                                                                                             N\A                                                                                                                                                                                             |
|  シンボル名  |                                                                                                                                                                         SSO_INFO_EXTERNAL_MAPPING_CONFLICT_ALLOWED                                                                                                                                                                          |
|  メッセージ テキスト   | Windows パスワードを変更すると、同じ外部システムの複数のアカウントも変更されます。%r<br /><br /> この外部システムのアダプターは、マッピングの競合を許可するように構成されているため、これは許可されます。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: % 2 %r<br /><br /> Windows アカウント: % 3 %r<br /><br /> 外部アカウント 1: % 4 %r<br /><br /> 外部アカウント 2: %5 |

## <a name="explanation"></a>説明  
 この情報イベントは、Windows パスワードを変更すると、同じ外部システムの複数のアカウントも変更されることを示します。  

## <a name="user-action"></a>ユーザーの操作  

-   ユーザーの操作は必要ありません。  

## <a name="more-info"></a>詳細

- **パスワード同期アダプターのプロパティ: オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]

- [パスワード同期](../core/password-synchronization2.md)
