---
title: シングル サインオン:イベント 10808 |Microsoft Docs
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
ms.openlocfilehash: ae819cd41cc39b4866ae2d9befc0edc3952cb5b8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380018"
---
# <a name="single-sign-on-event-10808"></a>シングル サインオン:イベント 10808
## <a name="details"></a>詳細  
  
|                 |                                                                  |
|-----------------|------------------------------------------------------------------|
|  製品名   |                    エンタープライズ シングル サインオン                     |
| 製品バージョン |    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]    |
|    イベント ID     |                              10808                               |
|  イベント ソース   |                              ENTSSO                              |
|    コンポーネント    |                               なし                                |
|  シンボル名  |                ENTSSO_E_HISSO_SYSTEM_NOT_ENABLED                 |
|  メッセージ テキスト   | ホスト側開始シングル サインオンは、SSO システムが有効になっていません。 |
  
## <a name="explanation"></a>説明  
 ホスト側開始シングル サインオンは、SSO システムが有効になっていません。  
  
## <a name="user-action"></a>ユーザーの操作  
 ホスト側開始シングル サインオンを構成するのにには、管理ツールを使用します。 これは、設定は、  
  
 グローバル情報の SSO_FLAG_SSO_EXTERNAL_TO_WINDOWS フラグ。