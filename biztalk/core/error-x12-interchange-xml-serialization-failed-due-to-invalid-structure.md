---
title: 無効な構造により、X12 インターチェンジの XML シリアル化に失敗しました。 TransactionSet または GE、ですが、見つかりません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d058fdbb-6be5-499f-86f7-0eb8a85c5fb2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b13b57d5f7dea8b48a88a70c6ad62d698f782e96
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388390"
---
# <a name="x12-interchange-xml-serialization-failed-due-to-invalid-structure-looking-for-transactionset-or-ge-but-not-found"></a>無効な構造により、X12 インターチェンジの XML シリアル化に失敗しました。 TransactionSet または GE を検索しましたが、見つかりませんでした
## <a name="details"></a>詳細  
  
|                 |                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------|
|  製品名   |                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                 |
| 製品バージョン |                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                             |
|    イベント ID     |                                                         -                                                          |
|  イベント ソース   |               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI               |
|    コンポーネント    |                                                     EDI エンジン                                                     |
|  シンボル名  |                                           X12TransactionSetOrGeNotFound                                            |
|  メッセージ テキスト   | 無効な構造により、X12 インターチェンジの XML シリアル化に失敗しました。 TransactionSet または GE を検索しましたが、見つかりませんでした |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、インターチェンジの構造が無効だったため、送信パイプラインで送信インターチェンジをシリアル化できなかったことを示します。 この理由として、必要なヘッダーまたはトレーラーが存在しないか、無効だった可能性があります。 これが発生するのは、グループのトランザクション セットの後に、別のトランザクション セットまたはグループ トレーラーが続いていない場合が考えられます。 また、構造的整合性チェックに失敗した可能性もあります。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジの構造を検証し、グループまたはトランザクション セットのヘッダーとトレーラーが有効であることを確認し、インターチェンジを再送信します。