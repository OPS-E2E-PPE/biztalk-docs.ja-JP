---
title: DocType が設定されていないために、トランザクション セットの処理後に発生したエラー |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a323658c-77d8-4059-aa15-d88c08e5450d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 874b0229eecdd5fe9c046f69789c4708b9280031
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240266"
---
# <a name="error-encountered-after-processing-transaction-sets-because-doctype-was-not-set"></a>DocType が設定されていないため、トランザクション セットの処理後にエラーが発生しました
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|DocTypeNotSet|  
|メッセージ テキスト|{0} トランザクション セットを処理した後でエラーが発生しました。 DocType が設定されていません。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、ST01 (X12 インターチェンジの場合) または UNH2.1 (EDIFACT インターチェンジの場合) がトランザクション セットに対して設定されなかったため、EDI 受信パイプラインで受信トランザクションを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、エラーの発生したトランザクション セットに対する ST01 または UNH1 セグメントが、有効なドキュメントの種類に設定されていることを確認します。