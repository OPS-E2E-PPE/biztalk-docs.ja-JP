---
title: トランザクション セット、サポートされているが |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ffe8528-f34f-4189-8ee6-4ae1afb50c92
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 908705bf733e7f95f771520ce9adee5a70dfe330
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279791"
---
# <a name="transaction-set-not-supported"></a>トランザクション セットがサポートされていません
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                              X12TsNotSupportedDescription                              |
|  メッセージ テキスト   |                             トランザクション セットがサポートされていません                              |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、トランザクション セットのドキュメントの種類に応じたドキュメント スキーマが展開されていないため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、トランザクション セットのドキュメントの種類に応じたドキュメント スキーマを展開します。