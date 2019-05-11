---
title: シングル サインオン:イベント 10590 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd8c3804-5c84-403f-881b-e4b101c2323a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21e9ed1ffdee369ccb357cb7b7f20424cb61b474
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65271028"
---
# <a name="single-sign-on-event-10590"></a>シングル サインオン:イベント 10590
## <a name="details"></a>詳細  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  製品名   |                 エンタープライズ シングル サインオン                  |
| 製品バージョン | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    イベント ID     |                           10590                            |
|  イベント ソース   |                           ENTSSO                           |
|    コンポーネント    |                            なし                             |
|  シンボル名  |                  SSO_ERROR_OUT_OF_SERVICE                  |
|  メッセージ テキスト   |        エンタープライズ シングル サインオンはオフラインになります。         |
  
## <a name="explanation"></a>説明  
 ENTSSO システムは、通常更新プログラムをチェック ENTSSO データベースで 30 秒ごとです。 データベース利用できない場合、指定した時間 (通常は 5 分)、システム自体がオフラインになります。 この状態で、システムは資格情報の要求に応答しません。 一部のオフラインおよび管理アクティビティは引き続き可能です。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーは、ENTSSO データベースがオフラインであることを示します。 すぐに調査する必要があります。