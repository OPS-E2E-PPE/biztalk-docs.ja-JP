---
title: 'シングル サインオン: イベント 10856 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10c06a86-e402-4adc-abbe-5ded923d626a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 707160ddfededefd5f0ef47e77df08844b38abcf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989347"
---
# <a name="single-sign-on-event-10856"></a>シングル サインオン: イベント 10856
## <a name="details"></a>詳細  
  
|                 |                                                                |
|-----------------|----------------------------------------------------------------|
|  製品名   |                   エンタープライズ シングル サインオン                    |
| 製品バージョン |   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]   |
|    イベント ID     |                             10856                              |
|  イベント ソース   |                             ENTSSO                             |
|    コンポーネント    |                              なし                               |
|  シンボル名  |               ENTSSO_E_MAPPING_CREATE_RESTRICTED               |
|  メッセージ テキスト   | アプリケーションのユーザーには、このアプリケーションのマッピングを作成できません。 |
  
## <a name="explanation"></a>説明  
 このアプリケーションは、Application Users グループのメンバーにマッピングの作成を許可するように構成されていませんでした。  
  
## <a name="user-action"></a>ユーザーの操作  
 十分な特権を持つユーザーにこのようなマッピングの作成を依頼する必要があります。