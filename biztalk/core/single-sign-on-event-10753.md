---
title: シングル サインオン:イベント 10753 |Microsoft Docs
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
ms.openlocfilehash: ca0c0066e1643ec6cc84f19eaf1ca5ece9822e69
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65307789"
---
# <a name="single-sign-on-event-10753"></a>シングル サインオン:イベント 10753
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
 このマッピングが既に存在するには既に使用されている Windows アカウントまたは外部のアカウント。  
  
## <a name="user-action"></a>ユーザーの操作  
 既存のマッピングおよび作成しようとしているマッピングを確認します。 既にマッピングが存在する場合は、それを使用し、新しいを削除します。 そうでない場合は、新しいを削除し、再作成します。