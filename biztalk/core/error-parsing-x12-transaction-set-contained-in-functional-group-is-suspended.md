---
title: 解析中に発生したエラーです。 X12 トランザクション セットの機能グループに含まれるは、次のエラーで中断されています |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51c6fa8e-d81c-4ccb-93b4-852ab184c4e9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66654a42c72ce65e22f5584bb906106a606fcdb7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388521"
---
# <a name="error-encountered-during-parsing-the-x12-transaction-set-contained-in-functional-group-is-being-suspended-with-following-errors"></a>解析中に発生したエラーです。 X12 トランザクション セットの機能グループに含まれるは、次のエラーで中断されています
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                      |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                          |
| 製品バージョン |                                                                                      [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                                      |
|    イベント ID     |                                                                                                                  -                                                                                                                   |
|  イベント ソース   |                                                                        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                                        |
|    コンポーネント    |                                                                                                              EDI エンジン                                                                                                              |
|  シンボル名  |                                                                                                    X12TransactionSetReceiveError                                                                                                     |
|  メッセージ テキスト   | 解析中に発生したエラーです。 X12 トランザクション セット id を持つ '{0}'機能グループ id に含まれている'{1}'、id を持つインターチェンジ内'{2}'、送信者 id '{3}'、受信者 id'{4}' 次のエラーで中断されています。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、EDI が受信することを示しますパイプライン、受信 X12 の解析中にエラーが発生しました、示されたエラー識別されたトランザクション セットのためのインターチェンジ。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、エラー メッセージの情報を使用してトランザクション セットのエラーを特定し、製品のヘルプで問題の解決方法を確認します。