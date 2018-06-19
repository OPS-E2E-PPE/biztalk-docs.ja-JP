---
title: 'インターチェンジで構造エラーが見つかりました。 最後の構造上有効な機能グループ ID が: |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bd62855b-ecc6-4cfd-be9c-0025348eb841
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 565a4865455cabef3cd53988d601a89ecf1549e0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241410"
---
# <a name="the-interchange-had-structural-error-last-structurally-valid-functional-group-id-was"></a>インターチェンジで構造エラーが見つかりました。 構造上有効な最後の機能グループ ID: 
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|X12InterchangeStructuralErrorAfter1stGroup|  
|メッセージ テキスト|Id '{0}'、送信者 id '{1}' で、インターチェンジ受信者 id '{2}' には、構造エラーが必要があります。 最後の構造上有効な機能グループ ID が '{3}'|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、表示された機能グループの後にインターチェンジで構造エラーが発生したため、受信パイプラインで受信 X12 インターチェンジを処理できなかったことを示します。 このイベントは保存中のインターチェンジで発生し、トランザクション セットはエラー時に中断された可能性があります。 このエラーにより、このエラーを含むトランザクション セット (複数可) は中断されましたが、それ以外のトランザクション セットは保存されたバッチの一部として処理されました。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジの送信者が構造上のエラーを修正した上で、インターチェンジを再送信してもらいます。