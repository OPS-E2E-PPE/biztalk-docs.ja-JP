---
title: シングル サインオン:イベント 10856 |Microsoft Docs
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
ms.openlocfilehash: 1ce753c055ed274624a08f5725dff5129b87f6b2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306578"
---
# <a name="single-sign-on-event-10856"></a>シングル サインオン:イベント 10856
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
 このアプリケーションは、アプリケーション ユーザー グループのメンバーは、マッピングを作成するのには許可されていませんように構成されました。  
  
## <a name="user-action"></a>ユーザーの操作  
 これらのマッピングを作成するための十分な特権を持つユーザーを確認する必要があります。