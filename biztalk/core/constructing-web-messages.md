---
title: Web メッセージの構築 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web messages, about Web messages
- Web messages, message types
- Web services, Web messages
- Web messages, parts
- Web messages
- messages, Web messages
ms.assetid: ca1792be-5fba-4f5d-a88e-b854f6a8ce33
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa03c7eae853677c22a0c7160075cad8bdb269cb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390324"
---
# <a name="constructing-web-messages"></a>Web メッセージの構築
Web メッセージの種類から Web メッセージを作成します。 Web 参照を追加すると、BizTalk には、Web メッセージの種類、BizTalk で、追加された Web サービスの Web メソッドに基づいて自動的に作成します。 Web メッセージは、Web メッセージの種類のいずれかにメッセージの種類の設定をオーケストレーションに追加します。 部分がプリミティブ .NET 型またはスキーマ型に基づいて個々 のメッセージを作成します。 メッセージ部分を含まない Web メッセージを構築することができます。  
  
 **Web メッセージの種類**  
  
 Web メッセージの種類、Reference.odx に定義されているは、変更、変更または削除できない点を除いて、通常のメッセージ型と同じです。 Web メッセージの種類を削除するには、BizTalk プロジェクトから Web 参照を削除する必要があります。  
  
 BizTalk プロジェクトは、追加された Web サービスで 1 つの要求と応答 Web メソッドごとに Web メッセージの種類を作成します。 Web メソッドが一方向の操作の場合は、BizTalk は要求を Web メッセージの種類のみを作成します。 Web メッセージの種類の要求には、Web メソッドの各入力パラメーターの 1 つのメッセージ部分が含まれています。 応答の Web メッセージの種類には、戻り値の 1 つのメッセージ部分と Web メソッドの場合は、各出力パラメーターの 1 つのメッセージ部分が含まれています。  
  
 Web メソッド パラメータ (入力または出力) によっては、BizTalk はプリミティブ .NET 型またはスキーマの種類から Web メッセージの種類を作成します。 Web メソッド パラメータがプリミティブ .NET 型の場合、メッセージ部分はプリミティブ .NET 型を使用します。 Web メソッド パラメータがスキーマ型の場合、BizTalk では、BizTalk プロジェクトにスキーマの種類を Reference.xsd 内のスキーマとして追加します。 スキーマは、メッセージ部分の基盤です。 Reference.xsd は Web 参照フォルダにあります。  
  
 また、作成できますプリミティブとスキーマの両方の .NET 型の .NET クラスを呼び出すことによって。 .NET クラスを使用してメッセージの種類を作成する方法の詳細については、次を参照してください。[ユーザー コードでのメッセージの構築](../core/constructing-messages-in-user-code.md)します。  
  
 **Web メッセージ**  
  
 Web メッセージは、(呼び出し)、Web サービスを使用する際に使用するメッセージです。 Web 参照を追加したときに、BizTalk によって作成された Web メッセージの種類のいずれかにメッセージの種類を設定する点を除いて、通常のメッセージを追加することと同様に、オーケストレーションを Web メッセージを追加します。  
  
 **メッセージ部分**  
  
 Web メッセージを作成した後は、個々 のメッセージ部分を構築します。 使用して、メッセージ部分がプリミティブ .NET 型を使用する場合、**メッセージの割り当て**図形。 使用して、メッセージ部分は、スキーマの種類を使用している場合、**変換**図形または**メッセージの割り当て**図形。 詳細については、次を参照してください。[ユーザー コードでのメッセージの構築](../core/constructing-messages-in-user-code.md)します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Web メッセージを追加する方法](../core/how-to-add-web-messages.md)  
  
-   [Web メッセージ部分の型を確認する方法](../core/how-to-determine-a-web-message-part-type.md)  
  
-   [プリミティブ .NET 型から Web メッセージ部分を構築する方法](../core/how-to-construct-a-web-message-part-from-a-primitive-net-type.md)  
  
-   [スキーマの種類から Web メッセージ部分を構築する方法](../core/how-to-construct-a-web-message-part-from-a-schema-type.md)  
  
-   [メッセージ部分を含まない Web メッセージを構築する方法](../core/how-to-construct-a-web-message-with-no-message-parts.md)