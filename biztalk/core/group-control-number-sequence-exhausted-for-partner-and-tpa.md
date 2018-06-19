---
title: パートナーと TPA の制御番号シーケンスが終了をグループ化 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cf341f8d-02ec-4618-a980-c8ac90654b1a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1850b968a2c9b4c8d2c16fd90d9e37d80b60f8b6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246402"
---
# <a name="group-control-number-sequence-exhausted-for-partner-and-tpa"></a>パートナーと TPA のグループ制御番号のシーケンスが終了しました
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|EdiControlNumberExhaustedForParty|  
|メッセージ テキスト|グループ制御番号のシーケンスを使い果たすと、TPA '{2}' のパートナー '{1}' です。 {2} - BizTalk Server 管理コンソールを使用して EDI プロパティでシーケンスをリセットします。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、BizTalk Server でのアグリーメントに {2} グループ制御の範囲が使い果たされたため、ドキュメントを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するのには、チェックを {2} アグリーメントの制御番号をリセットまたは制御番号の範囲を増やすか、アグリーメントでは、制御番号範囲指定に対するリセット ボタンをクリックします。