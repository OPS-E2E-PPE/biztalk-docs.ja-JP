---
title: 'シングル サインオン: イベント 10808 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b4efc1d-f163-4440-a78e-53065c6af36c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49d4e6ab0f6a9ea10ef28440f5b8399778fbc93b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971403"
---
# <a name="single-sign-on-event-10808"></a>シングル サインオン: イベント 10808
## <a name="details"></a>詳細  
  
|                 |                                                                  |
|-----------------|------------------------------------------------------------------|
|  製品名   |                    エンタープライズ シングル サインオン                     |
| 製品バージョン |    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]    |
|    イベント ID     |                              10808                               |
|  イベント ソース   |                              ENTSSO                              |
|    コンポーネント    |                               なし                                |
|  シンボル名  |                ENTSSO_E_HISSO_SYSTEM_NOT_ENABLED                 |
|  メッセージ テキスト   | SSO システムはホスト側開始シングル サインオンに対して有効になっていません。 |
  
## <a name="explanation"></a>説明  
 SSO システムはホスト側開始シングル サインオンに対して有効になっていません。  
  
## <a name="user-action"></a>ユーザーの操作  
 管理ツールを使用して、ホスト側開始シングル サインオンを構成します。 次の設定を行います  
  
 グローバル情報の SSO_FLAG_SSO_EXTERNAL_TO_WINDOWS フラグが設定されます。