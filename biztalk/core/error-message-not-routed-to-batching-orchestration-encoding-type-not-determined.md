---
title: メッセージをルーティングできません、バッチ処理オーケストレーションにエンコードの種類を特定できませんでした |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0d2ee38d-22c0-4fcf-bb68-b2ef00088c4c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe5054f53f779274c9b25f2751fdcb9d85545560
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241946"
---
# <a name="the-message-cannot-be-routed-to-the-batching-orchestration-as-the-encoding-type-could-not-be-determined"></a>エンコードの種類を決定できなかったため、バッチ処理オーケストレーションへメッセージをルーティングできません
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|バッチ処理エンジン|  
|シンボル名|UnknownEncodingType|  
|メッセージ テキスト|エンコードの種類を特定できなかったため、バッチ処理オーケストレーションへメッセージをルーティングできません。 バッチ処理を行うには、エンコードの種類が X12 または EDIFACT である必要があります。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、トランザクション セットがバッチ処理のフィルター条件を満たしていたにもかかわらず、非 EDI バッチ要素がバッチ処理オーケストレーション インスタンスにルーティングされなかったことを示します。 X12 を示す 0 または EDIFACT を示す 1 の値を使用した EDI.EncodingType コンテンツ プロパティの昇格が実行されなかったため、トランザクション セットをバッチ処理オーケストレーション インスタンスにルーティングすることができませんでした。 このエラーは、バッチ要素が BatchMarker パイプライン コンポーネントによってルーティング オーケストレーションにルーティングされたものの、非 EDI バッチ要素がマップによって EDI メッセージに変換されなかった場合に発生します。 その結果、ルーティング オーケストレーションは EDI ヘッダーからエンコードの種類を特定できません。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、非 EDI メッセージがルーティング オーケストレーションにルーティングされる前に、マップによって EDI メッセージに変換されていることを確認します。 また、非 EDI バッチ要素を処理するためのカスタム パイプライン コンポーネント (BatchMarker コンポーネントと共に) またはカスタム オーケストレーションを含める必要があります。 詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの「バッチ EDI インターチェンジのアセンブル」を参照してください。