---
title: 'シングル サインオン: イベント 10809 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7331d12b-1000-4a60-83b3-f092968e0e51
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d4bf5ba006af8c479abc621accdc28296c0eae3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016065"
---
# <a name="single-sign-on-event-10809"></a>シングル サインオン: イベント 10809
## <a name="details"></a>詳細  
  
|                 |                                                                   |
|-----------------|-------------------------------------------------------------------|
|  製品名   |                     エンタープライズ シングル サインオン                     |
| 製品バージョン |    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]     |
|    イベント ID     |                               10809                               |
|  イベント ソース   |                              ENTSSO                               |
|    コンポーネント    |                                なし                                |
|  シンボル名  |                  ENTSSO_E_HISSO_APP_NOT_ENABLED                   |
|  メッセージ テキスト   | アプリケーションはホスト側開始シングル サインオンに対して有効になっていません。 |
  
## <a name="explanation"></a>説明  
 アプリケーションはホスト側開始シングル サインオンに対して有効になっていません。  
  
## <a name="user-action"></a>ユーザーの操作  
 管理ツールを使用して、ホスト側開始シングル サインオンを構成します。 次の設定を行います  
  
 アプリケーションの SSO_FLAG_SSO_EXTERNAL_TO_WINDOWS フラグが設定されます。