---
title: パイプライン コンポーネントで受信データ ストリームの処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1b7c4f7-99ba-4bfa-89ab-1fabfe0845d1
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 691e0e28b8c3ab6cea273979a69d2eeba0135aa9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344663"
---
# <a name="handling-incoming-data-streams-in-pipeline-components"></a>パイプライン コンポーネントで受信データ ストリームの処理
カスタム逆アセンブラー パイプライン コンポーネント用にコードを記述する場合、次の考慮事項を行う必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
## <a name="do-not-close-the-incoming-data-stream-in-custom-dissasember-code"></a>カスタム逆アセンブラー コードでの受信データ ストリームを閉じない  
 カスタム逆アセンブラー パイプライン コンポーネント用にコードを記述するとき[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、逆アセンブラー コードでの受信データ ストリームが終了していないことを確認します。 入力メッセージからの受信ストリームは、共有リソースです。 受信ストリームは、メッセージ本文の追跡コンポーネントでも使用、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ エンジン。  
  
 追跡データが失われる可能性があり、メッセージ イベントとのサービス インスタンスの追跡を使用してストリーム データを確認できなく暗黙的または明示的に、受信ストリームを閉じる場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
## <a name="use-the-seek-method-of-the-stream-class-to-set-the-data-stream-pointer-to-the-start-of-the-stream"></a>Stream クラスの Seek メソッドを使用して、ストリームの先頭に、データ ストリーム ポインターを設定するには  
 ストリームの末尾に到達するまで、着信データ ストリームから読み取ることを確認します。 たとえば、カスタム コードが 300 KB のデータの読み取り要求を行うし、コードのみ 34 KB のデータを受信すると見なさないでくださいストリームの末尾に達したこと。 0 バイトのデータが返されるまで、カスタム コードは、受信ストリームから読み取り常にする必要があります。  
  
 カスタム コンポーネントでデータ ストリームを返す前に、ロジックはストリームの先頭に戻る、データ ストリーム ポインターを設定します。 たとえば、このコードは、seek メソッドを使用して、ストリームを返す前に、ストリームの先頭を指すようにするためのロジックを示しています。  
  
```  
myDataStream.Seek(0, SeekOrigin.Begin);  
return myDataStream;  
```  
  
 これを行わないし、現在のコンポーネントで最後に、ストリームは読み取り専用された場合、次のコンポーネントは、データ ストリーム ポインターがストリームの先頭に設定されていないため、空のストリームに見えるものを受け取ります。 後のパイプライン コンポーネントで予期しない解析と検証エラーができます。