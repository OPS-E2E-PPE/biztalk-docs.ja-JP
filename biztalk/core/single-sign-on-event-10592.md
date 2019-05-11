---
title: シングル サインオン:イベント 10592 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e044f9bd-c384-4f08-81f0-699e0c774c45
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0bfd622db90bbafcb4d2af1b45ae2b2286e3345c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65270949"
---
# <a name="single-sign-on-event-10592"></a>シングル サインオン:イベント 10592
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                             エンタープライズ シングル サインオン                                                              |
| 製品バージョン |                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                             |
|    イベント ID     |                                                                       10592                                                                        |
|  イベント ソース   |                                                                       ENTSSO                                                                       |
|    コンポーネント    |                                                                        なし                                                                         |
|  シンボル名  |                                                           SSO_WARN_TICKET_DECRYPT_FAILED                                                           |
|  メッセージ テキスト   | チケットの暗号化を解除できませんでした。 チケットが無効か expired.%r する可能性があります。<br /><br /> アプリケーション名: %1 %r<br /><br /> エラー コード: %2 |
  
## <a name="explanation"></a>説明  
 チケットが無効であるか、期限が切れている可能性があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 使用するチケットが有効でありが切れていないことを確認します。