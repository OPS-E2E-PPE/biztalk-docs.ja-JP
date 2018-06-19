---
title: 無効な AS2 の処理中に発生した名 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 84d848b5-b2a3-460d-85d4-c3576e4e3aaf
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26d26b929d20cef05c0bb71023a30afa43229fca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256874"
---
# <a name="invalid-as2-to-name-encountered-during-processing"></a>処理中に無効な AS2-To 名を検出しました
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|AS2 エンジン|  
|シンボル名|InvalidAS2ToNameEncounteredError|  
|メッセージ テキスト|処理中に無効な AS2-To 名を検出しました。  値: {0}|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、AS2-To ヘッダーの値が、AS2 RFC 4130 の仕様に準拠していなかったため、受信パイプラインで受信インターチェンジを処理できなかったか、または送信パイプラインで送信インターチェンジを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、受信メッセージまたは送信メッセージの AS2-To ヘッダーが、AS2 RFC 4130 のセクション 6.2 の仕様に準拠していることを確認します。