---
title: 'シングル サインオン: イベント 10753 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6b538083-180b-4a15-bedf-aac4fc351c30
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10fb7980b8c039c6ef02e52952564c581e88054b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969083"
---
# <a name="single-sign-on-event-10753"></a>シングル サインオン: イベント 10753
## <a name="details"></a>詳細  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  製品名   |                 エンタープライズ シングル サインオン                  |
| 製品バージョン | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    イベント ID     |                           10753                            |
|  イベント ソース   |                           ENTSSO                           |
|    コンポーネント    |                            なし                             |
|  シンボル名  |                  ENTSSO_E_MAPPING_EXISTS                   |
|  メッセージ テキスト   |                マッピングは既に存在します。                 |
  
## <a name="explanation"></a>説明  
 このマッピングは、使用中の Windows アカウントまたは外部アカウントに既に存在しています。  
  
## <a name="user-action"></a>ユーザーの操作  
 既存のマッピングおよび作成しようとしているマッピングを確認します。 必要なマッピングが既に存在している場合は、そのマッピングを使用し、新しいマッピングを削除します。 マッピングが存在しない場合は、新しいマッピングを削除して作成し直します。