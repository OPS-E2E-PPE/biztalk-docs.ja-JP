---
title: 解析中にエラーが発生しました。 機能グループに含まれる設定の Edifact トランザクションは、次のエラーで中断されています |Microsoft Docs
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
ms.openlocfilehash: 4b7e5dd86c995b78eb07aa9c7516274b748ee99b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014099"
---
# <a name="error-encountered-during-parsing-the-edifact-transaction-set-contained-in-functional-group-is-being-suspended-with-following-errors"></a>解析中にエラーが発生しました。 機能グループに含まれる EDIFACT トランザクション セットが次のエラーで中断されています
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                          |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                            |
| 製品バージョン |                                                                                        [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                                        |
|    イベント ID     |                                                                                                                    -                                                                                                                     |
|  イベント ソース   |                                                                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                                          |
|    コンポーネント    |                                                                                                                EDI エンジン                                                                                                                |
|  シンボル名  |                                                                                                     EfactTransactionSetReceiveError                                                                                                      |
|  メッセージ テキスト   | 解析中にエラーが発生しました。 Edifact トランザクション セット id を持つ '{0}'機能グループ id に含まれている'{1}'、id を持つインターチェンジ内'{2}'、送信者 id '{3}'、受信者 id'{4}' 次のエラーで中断されています。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、識別されたトランザクション セットで、示されたエラーが発生したため、EDI 受信パイプラインでグループの受信 EDIFACT インターチェンジを解析できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、エラー メッセージの情報を使用してトランザクション セットのエラーを特定し、ドキュメントで問題解決の方法を確認します。