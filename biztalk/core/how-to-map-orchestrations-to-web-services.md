---
title: Web サービスにオーケストレーションをマップする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, Web services
- BizTalk Web Services Publishing Wizard, naming conventions
- Web services, orchestrations
- orchestrations, naming conventions
- Web services, naming conventions
ms.assetid: e6a58978-c81c-49f3-9428-9bff60f1ded7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96fafc1179644b3299b674fe1b863a8ee8f9477d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336298"
---
# <a name="how-to-map-orchestrations-to-web-services"></a>Web サービスにオーケストレーションをマップする方法
オーケストレーションには、複数のポートを受信することができます。 BizTalk Web サービス公開ウィザードを使用して、選択した Web サービスとして公開するポートを受信します。 ウィザードは、受信ポートごとに 1 つの Web サービス (.asmx ファイル) を作成します。 同じ受信ポートの種類がある場合、ウィザードはすべての受信ポートの 1 つの Web サービスを作成もできます (一方向または要求/応答)。 操作では、関数呼び出しになります。 受信ポート内の各操作では、Web メソッドになります。 要求操作では、入力パラメーターになります。 応答操作では、戻り値の型になります。  
  
 要求と応答の操作が同じ Web メッセージの種類の場合は、入力パラメーターは次のようになります。、 **ref**戻り値の型と**void**します。 ASP.NET Web クライアントは、in、out、同じ型のパラメーターを組み合わせることで Web メソッドのシグネチャを変更することがあります。 ASP.NET Web クライアント可能性がありますから BizTalk Web メソッドを変更するなど、 **myService (文字列部分) を文字列**に**void myService (ref 文字列部分)** します。  
  
 操作メッセージの種類は、Web メソッドのシグネチャを定義します。 各メッセージの種類の部分は、Web メソッドのパラメーターです。  
  
## <a name="message-type-part-names-and-target-namespaces"></a>メッセージ型の要素の名前とターゲットの名前空間  
 ドキュメント スキーマとユーザー定義のクラスを**XmlRootAttribute**メッセージを指定されたターゲットの名前空間が定義されている種類の部分。 EDI スキーマ、せず、ユーザー定義クラス**XmlRootAttribute**指定、および組み込み型など**System.String**が定義されているターゲットの名前空間なしのメッセージの種類の部分。  
  
|メッセージの種類の部分名がある場合、|使用されるパラメーター名|  
|-----------------------------------------|-------------------------|  
|定義済みのターゲットの名前空間|ルート要素名|  
|定義されたターゲット名前空間がないです。|メッセージの種類の部分名|  
  
> [!NOTE]
>  応答メッセージでマルチパート メッセージの種類を使用すると、BizTalk Web サービス公開ウィザードでは、戻り値の最初のメッセージ部分と残りのメッセージ部分が出力パラメーターとして使用されます。  
  
## <a name="orchestrations-with-multiple-operations"></a>複数の操作とオーケストレーション  
 1 つの受信ポートが複数ではなく、オーケストレーションを設計する必要があります、オーケストレーションに複数の操作がある場合は、受信ポート。 この設計は、BizTalk Web サービス公開ウィザードが複数の Web サービス (.asmx) ファイルを作成するを防ぐし、すべての操作が同じ呼び出しパターンがある場合にのみ機能-すべての一方向操作またはすべての要求-応答操作。 受信ポートを 1 つの一方向の両方を含めることはできませんと要求/応答操作。  
  
> [!NOTE]
>  BizTalk Web サービス公開ウィザードが表示されますのパブリックの受信ポート。 パブリックの受信ポートがパブリック型修飾子でポートの種類。 Web サービスとして、パブリック ポートのみを発行できます。 既定のポートの種類は内部です。  
  
> [!NOTE]
>  場合、受信ポートが一方向として定義されている、Web メソッドの応答の種類は**void** Web クライアントに情報は返されません。 SOAP アダプターまたはオーケストレーションによってスローされた例外は、Web クライアントに返されません。  
  
## <a name="web-services-naming-conventions-for-published-orchestrations"></a>Web サービスの公開されたオーケストレーションの名前付け規則  
 BizTalk Web サービス公開ウィザードには、アンダー スコア、オーケストレーションの名前空間に基づく Web サービス (.asmx) ファイル名が生成されます (*)、その後にアンダー スコア、型名 (\\*)、および後に受信ポートの名前。 アンダー スコア (\_) ピリオドを含む部分で置き換えられます。 Web サービスの名前は、常にポートの名前を持ちます。  
  
 次の表では、BizTalk Web サービス公開ウィザードが Web サービス名がどのように生成するかを示します。  
  
|Web ポートとオーケストレーション|生成された Web サービスの名前|  
|-------------------------------------------|--------------------------------|  
|1 つの Web ポートの 1 つのオーケストレーション|orchestration1_port1.asmx|  
|2 つの Web ポートの 1 つのオーケストレーション|orchestration1_port1.asmx and orchestration1_port2.asmx|  
|各ポートの 1 つの Web の 2 つのオーケストレーション|orchestration1_port1.asmx and orchestration2_port2.asmx|  
  
## <a name="see-also"></a>参照  
 [Web サービスとしてのオーケストレーションの公開](../core/publishing-an-orchestration-as-a-web-service.md)   
 [BizTalk Web サービス公開ウィザードを使用して、オーケストレーションを Web サービスとして公開する方法](../core/publish-orchestration-as-web-service--biztalk-web-services-publishing-wizard.md)