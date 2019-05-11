---
title: シングル サインオン:イベント 10672 |Microsoft Docs
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
ms.openlocfilehash: 443c0bce458775f73c397cb0f1b1038665f328ba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397504"
---
# <a name="single-sign-on-event-10672"></a>シングル サインオン:イベント 10672
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                                                                                                                                                                                                                                |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                                                                                           エンタープライズ シングル サインオン                                                                                                                                                                                            |
| 製品バージョン |                                                                                                                                                                           [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                                           |
|    イベント ID     |                                                                                                                                                                                                     10672                                                                                                                                                                                                      |
|  イベント ソース   |                                                                                                                                                                                                     ENTSSO                                                                                                                                                                                                     |
|    コンポーネント    |                                                                                                                                                                                                      該当なし                                                                                                                                                                                                       |
|  シンボル名  |                                                                                                                                                                                 SSO_WARN_EXTERNAL_MAPPING_CONFLICT_NOT_ALLOWED                                                                                                                                                                                 |
|  メッセージ テキスト   | Windows パスワード変更原因となる 1 つ以上のアカウントへの変更に同じ外部 system.%r<br /><br /> この外部システムのアダプタがマッピング conflicts.%r を許可しないように構成されているため、これは、許可されていません<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: % 2 %r<br /><br /> Windows アカウント: % 3 %r<br /><br /> 外部アカウント 1: % 4 %r<br /><br /> 外部アカウント 2: %5 |

## <a name="explanation"></a>説明  
 この警告イベントは、こと、Windows パスワード変更原因となる 1 つ以上のアカウントへの変更、同じ外部システムのことを示します。 アダプターの構成で許可されないため、この変更を実行できません。  

## <a name="user-action"></a>ユーザーの操作  

-   SSO 管理ツールを使用して、構成、**マッピングの競合を許可する**パスワード同期アダプターのプロパティ。  

## <a name="more-info"></a>詳細情報

- **パスワード同期アダプターのプロパティ:オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]

- [パスワード同期](../core/password-synchronization2.md)
