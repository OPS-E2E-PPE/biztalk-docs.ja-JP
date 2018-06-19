---
title: 文字範囲を制限する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e12213bf-750e-43a2-998a-949fa4255b73
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74f1399aaa828d5c23c2600ebabeb7063a982447
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268290"
---
# <a name="restricted-character-ranges"></a>文字範囲の制限

## <a name="overview"></a>概要
フラット ファイル メッセージのスキーマを作成する場合、特定の文字または文字範囲が送信メッセージに格納されないよう [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に指示を与えることができます。 これを行うには、BizTalk エディターで、送信先スキーマとして使用されるスキーマを開きます。 選択、**スキーマ**ノードと、使用、**文字の制限**プロパティを開くには、**文字の制限** ダイアログ ボックス。 範囲をできないようにする BizTalk Server によって送信されるメッセージに含まれる文字を入力し、クリックして**OK**です。 BizTalk Server がで指定された文字を処理しようとしたときに、**文字の制限**処理が停止し、エラー メッセージを送信先スキーマのダイアログ ボックスを生成します。  
  
> [!NOTE]
>  BizTalk Server の文字範囲の制限は、フラット ファイル拡張子の機能です。このため、XML メッセージには適用されません。 さまざまな種類のメッセージに今後提供される可能性のある拡張機能は、対応するメッセージ形式の文字範囲の制限の実装方法によって異なる場合があります。  
  
## <a name="see-also"></a>参照  
-  [ファイル メッセージ スキーマをフラットを作成する際の考慮事項](../core/considerations-when-creating-flat-file-message-schemas.md)   
-  **文字の制限 (フラット ファイル スキーマのノード プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]