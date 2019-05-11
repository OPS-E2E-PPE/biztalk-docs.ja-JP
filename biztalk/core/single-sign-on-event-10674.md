---
title: シングル サインオン:イベント 10674 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad0c0d9e-1e6d-4c3e-86e0-9e336a18f3d6
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f10f76d2d1be51271912b00110bb02f7009cfbc0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397486"
---
# <a name="single-sign-on-event-10674"></a>シングル サインオン:イベント 10674
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                                                                                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                                                                                  エンタープライズ シングル サインオン                                                                                                                                                                                  |
| 製品バージョン |                                                                                                                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                                  |
|    イベント ID     |                                                                                                                                                                                            10674                                                                                                                                                                                            |
|  イベント ソース   |                                                                                                                                                                                           ENTSSO                                                                                                                                                                                            |
|    コンポーネント    |                                                                                                                                                                                             該当なし                                                                                                                                                                                             |
|  シンボル名  |                                                                                                                                                                        SSO_WARN_WINDOWS_MAPPING_CONFLICT_NOT_ALLOWED                                                                                                                                                                        |
|  メッセージ テキスト   | 外部パスワードを変更する原因となる 1 つ以上の Windows account.%r への変更<br /><br /> この外部システムのアダプタがマッピング conflicts.%r を許可しないように構成されているため、これは、許可されていません<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: % 2 %r<br /><br /> 外部アカウント: % 3 %r<br /><br /> Windows アカウント 1: % 4 %r<br /><br /> Windows アカウント 2: %5 |

## <a name="explanation"></a>説明  
 この警告イベントは、1 つ以上の Windows アカウントに変更は、外部パスワード変更しようとしたことを示します。 アダプターの構成で許可されないため、この変更を実行できません。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  

-   マッピングの競合が予想され、許可される場合、は、SSO 管理ツールを使用して、構成する、**マッピングの競合を許可する**パスワード同期アダプターのプロパティ。  

## <a name="more-info"></a>詳細情報

- **パスワード同期アダプターのプロパティ:オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]

- [パスワード同期](../core/password-synchronization2.md)
