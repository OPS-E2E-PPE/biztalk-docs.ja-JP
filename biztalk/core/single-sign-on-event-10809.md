---
title: シングル サインオン:イベント 10809 |Microsoft Docs
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
ms.openlocfilehash: 3dc0f1b98ed1b9b3e414888b01f2693a9f1786f4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65293003"
---
# <a name="single-sign-on-event-10809"></a>シングル サインオン:イベント 10809
## <a name="details"></a>詳細  
  
|                 |                                                                   |
|-----------------|-------------------------------------------------------------------|
|  製品名   |                     エンタープライズ シングル サインオン                     |
| 製品バージョン |    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]     |
|    イベント ID     |                               10809                               |
|  イベント ソース   |                              ENTSSO                               |
|    コンポーネント    |                                なし                                |
|  シンボル名  |                  ENTSSO_E_HISSO_APP_NOT_ENABLED                   |
|  メッセージ テキスト   | ホスト側開始シングル サインオンは、アプリケーションが有効になっていません。 |
  
## <a name="explanation"></a>説明  
 ホスト側開始シングル サインオンは、アプリケーションが有効になっていません。  
  
## <a name="user-action"></a>ユーザーの操作  
 ホスト側開始シングル サインオンを構成するのにには、管理ツールを使用します。 これは、設定は、  
  
 アプリケーションの SSO_FLAG_SSO_EXTERNAL_TO_WINDOWS フラグ。