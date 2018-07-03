---
title: 'シングル サインオン: イベント 10674 |Microsoft Docs'
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
ms.openlocfilehash: 97f67258bb1ee9118c6f462d0eded4b8f238707b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996131"
---
# <a name="single-sign-on-event-10674"></a>シングル サインオン: イベント 10674
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                                                                                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                                                                                  エンタープライズ シングル サインオン                                                                                                                                                                                  |
| 製品バージョン |                                                                                                                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                                  |
|    イベント ID     |                                                                                                                                                                                            10674                                                                                                                                                                                            |
|  イベント ソース   |                                                                                                                                                                                           ENTSSO                                                                                                                                                                                            |
|    コンポーネント    |                                                                                                                                                                                             N\A                                                                                                                                                                                             |
|  シンボル名  |                                                                                                                                                                        SSO_WARN_WINDOWS_MAPPING_CONFLICT_NOT_ALLOWED                                                                                                                                                                        |
|  メッセージ テキスト   | 外部パスワード変更によって、複数の Windows アカウントを変更しようとしました。%r<br /><br /> この外部システムのアダプターは、マッピングの競合を許可しないよう構成されているため、実行できません。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: % 2 %r<br /><br /> 外部アカウント: % 3 %r<br /><br /> Windows アカウント 1: % 4 %r<br /><br /> Windows アカウント 2: %5 |

## <a name="explanation"></a>説明  
 この警告イベントは、外部パスワード変更によって、複数の Windows アカウントを変更しようとしたことを示します。 アダプター構成で許可されないため、この変更を実行できません。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  

-   マッピングの競合が予想され、許可される場合、は、SSO 管理ツールを使用して、構成する、**マッピングの競合を許可する**パスワード同期アダプターのプロパティ。  

## <a name="more-info"></a>詳細

- **パスワード同期アダプターのプロパティ: オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]

- [パスワード同期](../core/password-synchronization2.md)
