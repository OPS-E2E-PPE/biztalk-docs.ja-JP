---
title: 解析中に発生したエラーです。 機能グループに含まれる設定の Edifact トランザクションは、次のエラーで中断されています |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 986a7220-d35a-4047-8996-7d44c7d2b823
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19f6332f1f1f7f97c9dd69f34ae221e120770958
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389038"
---
# <a name="error-encountered-during-parsing-the-edifact-transaction-set-contained-in-functional-group-is-being-suspended-with-following-errors"></a>解析中に発生したエラーです。 機能グループに含まれる Edifact トランザクション セットは、次のエラーで中断されています
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                          |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                            |
| 製品バージョン |                                                                                        [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                                        |
|    イベント ID     |                                                                                                                    -                                                                                                                     |
|  イベント ソース   |                                                                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                                          |
|    コンポーネント    |                                                                                                                EDI エンジン                                                                                                                |
|  シンボル名  |                                                                                                     EfactTransactionSetReceiveError                                                                                                      |
|  メッセージ テキスト   | 解析中に発生したエラーです。 Edifact トランザクション セット id を持つ '{0}'機能グループ id に含まれている'{1}'、id を持つインターチェンジ内'{2}'、送信者 id '{3}'、受信者 id'{4}' 次のエラーで中断されています。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントを示します、EDI 受信パイプラインは、識別されたトランザクション セット、示されたエラーのため、グループで受信 EDIFACT インターチェンジを解析できませんでした。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、エラー メッセージの情報を使用してトランザクション セットのエラーを特定し、ドキュメントで問題の解決方法を確認します。