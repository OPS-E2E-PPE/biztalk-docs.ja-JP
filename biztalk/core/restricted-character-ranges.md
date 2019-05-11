---
title: 文字範囲の制限 |Microsoft Docs
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
ms.openlocfilehash: add7cfdf529d21c7ed54ae60d1c39c39266af6fb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255112"
---
# <a name="restricted-character-ranges"></a>文字範囲の制限

## <a name="overview"></a>概要
フラット ファイル メッセージのスキーマを作成するときに指示できます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]特定の文字または送信メッセージに含まれている文字の範囲をブロックします。 BizTalk エディターで、これは、送信先スキーマとして使用するスキーマを開きます。 選択、**スキーマ**ノードと、使用して、**文字の制限**プロパティを開き、**文字の制限** ダイアログ ボックス。 範囲をできないようにする BizTalk Server によって送信されたメッセージに含まれる文字を入力し、クリックして**OK**します。 BizTalk Server がで指定された文字を処理しようとしたときに、**文字の制限**の処理が停止し、エラー メッセージを送信先スキーマ ダイアログ ボックスが生成されます。  

> [!NOTE]
>  BizTalk server の文字範囲の制限は、フラット ファイル拡張子の関数であり、XML メッセージには適用されません。 文字範囲の制限、サポートされているメッセージ形式の実装方法が異なるさまざまな種類のメッセージを今後提供される可能性の拡張機能。  

## <a name="see-also"></a>参照  
- [フラット ファイル メッセージ スキーマを作成する上での注意点](../core/considerations-when-creating-flat-file-message-schemas.md)   
- **文字の制限 (フラット ファイル スキーマのノード プロパティ** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
