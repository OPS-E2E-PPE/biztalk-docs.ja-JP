---
title: 'シングル サインオン: イベント 10592 |Microsoft Docs'
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
ms.openlocfilehash: b9fdf7259de2217c2e6cd616f58b3b1118bf991c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017258"
---
# <a name="single-sign-on-event-10592"></a>シングル サインオン: イベント 10592
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                             エンタープライズ シングル サインオン                                                              |
| 製品バージョン |                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                             |
|    イベント ID     |                                                                       10592                                                                        |
|  イベント ソース   |                                                                       ENTSSO                                                                       |
|    コンポーネント    |                                                                        なし                                                                         |
|  シンボル名  |                                                           SSO_WARN_TICKET_DECRYPT_FAILED                                                           |
|  メッセージ テキスト   | チケットを暗号化解除できませんでした。 チケットが有効ではないか、期限切れの可能性があります。%r<br /><br /> アプリケーション名: %1 %r<br /><br /> エラー コード: %2 |
  
## <a name="explanation"></a>説明  
 チケットが有効ではないか、期限切れの可能性があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 使用するチケットが有効で、期限が切れていないことを確認します。