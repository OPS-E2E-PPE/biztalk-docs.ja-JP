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
ms.openlocfilehash: f624c94a22efbfa56ae533ff9bfdbf3276776f8a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998587"
---
# <a name="how-to-map-orchestrations-to-web-services"></a>Web サービスにオーケストレーションをマップする方法
オーケストレーションには、複数の受信ポートを設定できます。 BizTalk Web サービス公開ウィザードを使用して、Web サービスとして公開する受信ポートを選択します。 このウィザードでは、受信ポートごとに 1 つの Web サービス (.asmx ファイル) が作成されます。 また、すべての受信ポートに対して 1 つの Web サービスが作成されます (すべて同じ種類 (一方向または要求 - 応答) の受信ポートである場合)。 操作は関数呼び出しになります。 受信ポートでの各操作は Web メソッドになり、 要求操作は入力パラメータになります。 応答操作は戻り値の型になります。  
  
 要求と応答の操作が同じ Web メッセージの種類の場合は、入力パラメーターは次のようになります。、 **ref**戻り値の型と**void**します。 ASP.NET Web クライアントは、同じ種類の入力および出力パラメータを組み合わせて、Web メソッドの署名を変更することができます。 ASP.NET Web クライアント可能性がありますから BizTalk Web メソッドを変更するなど、 **myService (文字列部分) を文字列**に**void myService (ref 文字列部分)** します。  
  
 操作メッセージの種類によって Web メソッドの署名が定義されます。 また、各メッセージの種類の部分が Web メソッドのパラメータになります。  
  
## <a name="message-type-part-names-and-target-namespaces"></a>メッセージの種類の部分名とターゲットの名前空間  
 ドキュメント スキーマとユーザー定義のクラスを**XmlRootAttribute**メッセージを指定されたターゲットの名前空間が定義されている種類の部分。 EDI スキーマ、せず、ユーザー定義クラス**XmlRootAttribute**指定、および組み込み型など**System.String**が定義されているターゲットの名前空間なしのメッセージの種類の部分。  
  
|メッセージの種類の部分名に設定されている内容|使用されるパラメータ名|  
|-----------------------------------------|-------------------------|  
|ターゲットの名前空間が定義されている|ルート要素名|  
|ターゲットの名前空間が定義されていない|メッセージの種類の部分名|  
  
> [!NOTE]
>  応答メッセージにマルチパート メッセージの種類が使用されていると、BizTalk Web サービス公開ウィザードは、最初のメッセージ部分を戻り値に使用し、残りのメッセージ部分は出力パラメータとして使用します。  
  
## <a name="orchestrations-with-multiple-operations"></a>複数の操作を含むオーケストレーション  
 オーケストレーションに複数の操作が含まれる場合、複数の送信ポートではなく 1 つの送信ポートを使用するようにオーケストレーションを設計する必要があります。 この設計は、BizTalk Web サービス公開ウィザードが複数の Web サービス (.asmx) ファイルを作成するを防ぐし、すべての操作が同じ呼び出しパターンがある場合にのみ機能-すべての一方向操作またはすべての要求-応答操作。 単一の受信ポートに、一方向の操作と要求 - 応答操作の両方を含めることはできません。  
  
> [!NOTE]
>  BizTalk Web サービス公開ウィザードは、パブリックの受信ポートを表示します。 パブリックの受信ポートは、パブリックの型修飾子を持つ種類のポートです。 パブリック ポートは、Web サービスとしてのみ公開できます。 既定のポートの種類は "内部" です。  
  
> [!NOTE]
>  場合、受信ポートが一方向として定義されている、Web メソッドの応答の種類は**void** Web クライアントに情報は返されません。 SOAP アダプタやオーケストレーションによってスローされる例外は、Web クライアントには返されません。  
  
## <a name="web-services-naming-conventions-for-published-orchestrations"></a>公開オーケストレーションの Web サービスの名前付け規則  
 BizTalk Web サービス公開ウィザードには、アンダー スコア、オーケストレーションの名前空間に基づく Web サービス (.asmx) ファイル名が生成されます (*)、その後にアンダー スコア、型名 (\\*)、および後に受信ポートの名前。 アンダー スコア (\_) ピリオドを含む部分で置き換えられます。 Web サービスの名前には、必ず、ポート名が付加されます。  
  
 次の表を使用して、BizTalk Web サービス公開ウィザードが Web サービス名を生成する方法を説明します。  
  
|オーケストレーションの数 (含まれる Web ポートの数)|生成される Web サービス名|  
|-------------------------------------------|--------------------------------|  
|1 つのオーケストレーション (1 つの Web ポートを含む)|orchestration1_port1.asmx|  
|1 つのオーケストレーション (2 つの Web ポートを含む)|orchestration1_port1.asmx と orchestration1_port2.asmx|  
|2 つのオーケストレーション (それぞれ 1 つの Web ポートを含む)|orchestration1_port1.asmx と orchestration2_port2.asmx|  
  
## <a name="see-also"></a>参照  
 [Web サービスとしてのオーケストレーションの公開](../core/publishing-an-orchestration-as-a-web-service.md)   
 [BizTalk Web サービス公開ウィザードを使用して、オーケストレーションを Web サービスとして公開する方法](../core/publish-orchestration-as-web-service--biztalk-web-services-publishing-wizard.md)