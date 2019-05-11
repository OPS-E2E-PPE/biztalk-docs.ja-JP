---
title: シングル サインオン:イベント 10765 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e28fe42e-aa2b-4be4-b757-bc9c5c37526b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f509bb4a00bc4f1e77b09fa0b93ccaf7d50ad0ca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394303"
---
# <a name="single-sign-on-event-10765"></a>シングル サインオン:イベント 10765
## <a name="details"></a>詳細  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  製品名   |                 エンタープライズ シングル サインオン                  |
| 製品バージョン | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    イベント ID     |                           10765                            |
|  イベント ソース   |                           ENTSSO                           |
|    コンポーネント    |                            なし                             |
|  シンボル名  |                  ENTSSO_E_NO_CREDENTIALS                   |
|  メッセージ テキスト   |       マッピングの資格情報が設定されていません。        |
  
## <a name="explanation"></a>説明  
 マッピングに対して getcredentials が要求したされ、指定されたマッピングには、資格情報はありません。  
  
## <a name="user-action"></a>ユーザーの操作  
 コマンドラインまたは MMC スナップインを使用して、マッピングの資格情報を設定します。