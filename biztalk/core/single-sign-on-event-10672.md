---
title: 'シングル サインオン: イベント 10672 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2422c7d-51bc-4f12-8830-193d71d2bce9
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 39a8dd5e65b513ceabf2c654dcb5cf083d6f1295
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000763"
---
# <a name="single-sign-on-event-10672"></a>シングル サインオン: イベント 10672
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                                                                                                                                                                                                                                |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                                                                                           エンタープライズ シングル サインオン                                                                                                                                                                                            |
| 製品バージョン |                                                                                                                                                                           [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                                           |
|    イベント ID     |                                                                                                                                                                                                     10672                                                                                                                                                                                                      |
|  イベント ソース   |                                                                                                                                                                                                     ENTSSO                                                                                                                                                                                                     |
|    コンポーネント    |                                                                                                                                                                                                      N\A                                                                                                                                                                                                       |
|  シンボル名  |                                                                                                                                                                                 SSO_WARN_EXTERNAL_MAPPING_CONFLICT_NOT_ALLOWED                                                                                                                                                                                 |
|  メッセージ テキスト   | 同じ外部システムの複数のアカウントを変更するような Windows パスワードの変更が行われました。%r<br /><br /> この外部システムのアダプターは、マッピングの競合を許可しないよう構成されているため、実行できません。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: % 2 %r<br /><br /> Windows アカウント: % 3 %r<br /><br /> 外部アカウント 1: % 4 %r<br /><br /> 外部アカウント 2: %5 |

## <a name="explanation"></a>説明  
 この警告イベントは、同じ外部システムの複数のアカウントを変更するような Windows パスワードの変更が行われたことを示します。%r アダプター構成で許可されないため、この変更を実行できません。  

## <a name="user-action"></a>ユーザーの操作  

-   SSO 管理ツールを使用して、構成、**マッピングの競合を許可する**パスワード同期アダプターのプロパティ。  

## <a name="more-info"></a>詳細

- **パスワード同期アダプターのプロパティ: オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]

- [パスワード同期](../core/password-synchronization2.md)
