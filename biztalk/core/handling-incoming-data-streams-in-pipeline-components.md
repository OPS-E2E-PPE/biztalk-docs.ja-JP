---
title: パイプライン コンポーネントで受信したデータ ストリームを処理 |Microsoft ドキュメント
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
ms.openlocfilehash: 20fc34da3a5c8e65f81cd6bbbb699f52506cdc6b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246570"
---
# <a name="handling-incoming-data-streams-in-pipeline-components"></a>パイプライン コンポーネントでの受信データ ストリームの処理
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のパイプライン コンポーネント用にカスタム逆アセンブラー コードを記述する場合は、次のことを考慮する必要があります。  
  
## <a name="do-not-close-the-incoming-data-stream-in-custom-dissasember-code"></a>カスタム逆アセンブラー コードで受信データ ストリームを閉じない  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のパイプライン コンポーネント用にカスタム逆アセンブラー コードを記述する場合は、逆アセンブラー コードで受信データ ストリームを閉じないようにしてください。 入力メッセージからの受信ストリームは共有リソースであり、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] メッセージ エンジンの、メッセージ本文の追跡コンポーネントでも使用されます。  
  
 暗黙的せよ明示的にせよ、受信ストリームを閉じると追跡データが失われる可能性があります。この場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のメッセージ イベントとサービス インスタンスの追跡でストリーム データを確認できなくなります。  
  
## <a name="use-the-seek-method-of-the-stream-class-to-set-the-data-stream-pointer-to-the-start-of-the-stream"></a>Stream クラスの Seek メソッドを使い、データ ストリーム ポインターをストリームの先頭に設定する  
 受信データ ストリームから、ストリームの末尾に達するまで確実にデータを読み込むようにしてください。 たとえば、カスタム コードで 300 KB のデータの読み取り要求を発行し、34 KB のデータしか受信していない場合は、ストリームの末尾に達していません。 カスタム コードでは常に、残り 0 バイトになるまで受信ストリームから読み込む必要があります。  
  
 カスタム コンポーネント ロジックでデータ ストリームを返す前に、データ ストリーム ポインターをストリームの先頭に戻してください。 たとえば、このコードは、ストリームを返す前に、ストリームの先頭を指す seek メソッドを使用するためのロジックを示しています。  
  
```  
myDataStream.Seek(0, SeekOrigin.Begin);  
return myDataStream;  
```  
  
 この操作を行わずに現在のコンポーネントでストリームを最後まで読み込んだ場合は、データ ストリーム ポインターがストリームの先頭にないため、次のコンポーネントで受信するストリームは空のストリームになります。 これは、後のパイプライン コンポーネントで予期しない解析エラーや検証エラーが発生する原因となります。