---
title: Web メッセージの構築 |Microsoft ドキュメント
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
ms.openlocfilehash: 8c344bbb836a6524ec1fd2656a5ba3f8bc8fad7d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237986"
---
# <a name="constructing-web-messages"></a>Web メッセージの構築
[Web メッセージの種類] から Web メッセージを構築します。 Web 参照を追加すると、BizTalk では、追加された Web サービスの Web メソッドに基づいて Web メッセージの種類が自動的に作成されます。 Web メッセージをオーケストレーションに追加するには、メッセージの種類を Web メッセージの種類のいずれかに設定します。 プリミティブ .NET 型またはスキーマ型に基づいて、個々のメッセージ部分を作成します。 メッセージ部分を含まない Web メッセージも構築できます。  
  
 **Web メッセージの種類**  
  
 Web メッセージの種類は、Reference.odx に定義されています。Web メッセージの種類は、通常のメッセージの種類と同じですが、変更、名前変更、および削除を行うことはできません。 Web メッセージの種類を削除するには、BizTalk プロジェクトから Web 参照を削除する必要があります。  
  
 BizTalk プロジェクトは、追加された Web サービスにある Web メソッドごとに、要求に使用する Web メッセージの種類を 1 つ、応答に使用する Web メッセージの種類を 1 つ作成します。 Web メソッドが一方向の操作である場合、BizTalk は要求に使用する Web メッセージの種類のみを作成します。 要求に使用する Web メッセージの種類には、Web メソッドの入力パラメータごとに 1 つのメッセージ部分が含まれます。 応答に使用する Web メッセージの種類には、戻り値を格納するためのメッセージ部分が含まれ、Web メソッドの出力パラメータごとに 1 つのメッセージ部分が含まれます。  
  
 Web メソッド パラメータ (入力または出力) に応じて、BizTalk はプリミティブ .NET 型またはスキーマ型から Web メッセージの種類を作成します。 Web メソッド パラメータがプリミティブ .NET 型である場合、メッセージ部分はプリミティブ .NET 型を使用します。 Web メソッド パラメータがスキーマ型である場合、BizTalk は BizTalk プロジェクトに Reference.xsd 内のスキーマとして、スキーマ型を追加します。 このスキーマがメッセージ部分の基礎になります。 Reference.xsd は Web 参照フォルダにあります。  
  
 別の方法として、.NET クラスを呼び出すことで、プリミティブ .NET 型とスキーマ .NET 型の両方を作成できます。 .NET クラスを使用してメッセージの種類を作成する方法の詳細については、次を参照してください。[ユーザー コードでメッセージを構築する](../core/constructing-messages-in-user-code.md)です。  
  
 **Web メッセージ**  
  
 Web メッセージは、Web サービスを利用 (呼び出し) するときに使用するメッセージです。 Web メッセージは、通常のメッセージと同様にオーケストレーションに追加できます。ただし、メッセージの種類を、Web 参照を追加するときに作成されたいずれかの Web メッセージの種類に設定する必要があります。  
  
 **メッセージ部分**  
  
 Web メッセージを作成したら、個々のメッセージ部分を構築します。 使用する、メッセージ部分は、プリミティブ .NET 型を使用している場合、**メッセージの割り当て**図形です。 使用する、メッセージ部分は、スキーマの種類を使用している場合、**変換**図形または**メッセージの割り当て**図形です。 詳細については、次を参照してください。[ユーザー コードでメッセージを構築する](../core/constructing-messages-in-user-code.md)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Web メッセージを追加する方法](../core/how-to-add-web-messages.md)  
  
-   [Web メッセージ部分の型を確認する方法](../core/how-to-determine-a-web-message-part-type.md)  
  
-   [プリミティブ .NET 型から Web メッセージ部分を構築する方法](../core/how-to-construct-a-web-message-part-from-a-primitive-net-type.md)  
  
-   [スキーマの種類から Web メッセージ部分を構築する方法](../core/how-to-construct-a-web-message-part-from-a-schema-type.md)  
  
-   [メッセージ部分を含まない Web メッセージを構築する方法](../core/how-to-construct-a-web-message-with-no-message-parts.md)