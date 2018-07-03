---
title: 'シングル サインオン: イベント 10765 |Microsoft Docs'
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
ms.openlocfilehash: bd49ead3fc30d3b98ea804a98a5882696ea749d7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975107"
---
# <a name="single-sign-on-event-10765"></a>シングル サインオン: イベント 10765
## <a name="details"></a>詳細  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  製品名   |                 エンタープライズ シングル サインオン                  |
| 製品バージョン | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    イベント ID     |                           10765                            |
|  イベント ソース   |                           ENTSSO                           |
|    コンポーネント    |                            なし                             |
|  シンボル名  |                  ENTSSO_E_NO_CREDENTIALS                   |
|  メッセージ テキスト   |       マッピングに対して資格情報が設定されていません。        |
  
## <a name="explanation"></a>説明  
 マッピングに対して GetCredentials が要求されましたが、指定されたマッピングには資格情報がありません。  
  
## <a name="user-action"></a>ユーザーの操作  
 コマンド ラインまたは MMC スナップインを使用して、マッピングに資格情報を設定します。