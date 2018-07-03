---
title: 見つからないか無効か重複するトランザクション セット識別子 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8580aab2-9fa4-43fb-b643-10621926591e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 476b510396d29d5f4e85a13ed7c3bca3ee3fcef3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971723"
---
# <a name="missing-or-invalid-or-duplicate-transaction-set-identifier"></a>トランザクション セット識別子が見つからないか、無効か、重複しています
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                      X12TsMissingOrInvalidTsIdentiferDescription2                      |
|  メッセージ テキスト   |            見つからないか無効か重複するトランザクション セット識別子 '{0}'            |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、トランザクション セット ID の値 (ST01 フィールド) がないか、重複していたか、値が無効であったため、受信または送信パイプラインで X12 インターチェンジを処理できなかったことを示します。 このエラーが発生する場合は、ドキュメント スキーマに ST ヘッダーと SE トレーラーがない可能性があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジに ST01 フィールドの値があり、スキーマに ST ヘッダーと SE トレーラーのエントリがあることを確認します。 ST01 の値が、3 桁の有効なドキュメント型の識別子であることを確認します。 ST01 フィールドが、別のトランザクション セットの ST01 フィールドと重複していないことを確認します。