---
title: Web サービスを公開する場合の考慮事項 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, publishing
- Web services, planning
- Web services, schemas
- schemas, Web services
ms.assetid: 3ace0260-a1cb-4e59-a820-36ee7d5cceda
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 825a16555f0b0c82282ae4d85592567d2a19c073
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="considerations-when-publishing-web-services"></a>Web サービスを公開する際の考慮事項
ここでは、Web サービスを公開する前に考慮が必要な情報について説明します。  
  
## <a name="publishing-schemas-and-the-include-element"></a>スキーマおよび include 要素の公開  
 いくつかのシナリオがある場所が含まれたスキーマ、 **含める** 要素は、Web サービスとして発行できません。 BizTalk Web サービス公開ウィザードを完了するときに、エラーが発生します。 これらの制限は以下のとおりです。  
  
-   循環が含まれています (インクルードされるスキーマは、 **含める** をインクルードするスキーマの要素)  
  
-   未解決 **schemaLocation** 属性には、エラーが発生  
  
 制限の詳細については要素を含めるに「含める要素のバインディング サポート」を参照してください[ http://go.microsoft.com/fwlink/?LinkId=62312](http://go.microsoft.com/fwlink/?LinkId=62312)です。  
  
## <a name="publishing-schemas-and-the-import-element"></a>スキーマおよび import 要素の公開  
 BizTalk Web サービス公開ウィザードには、.NET Framework に付属する XSD.exe と同じ制限があります。 詳細についてで「Import 要素のバインディング サポート」を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=62311](http://go.microsoft.com/fwlink/?LinkId=62311)です。  
  
## <a name="publishing-schemas-and-the-redefine-element"></a>スキーマおよび redefine 要素の公開  
 BizTalk Web サービス公開ウィザードには、.NET Framework に付属する XSD.exe と同じ制限があります。 詳細についてで「Redefine 要素バインディング サポート」を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=62313](http://go.microsoft.com/fwlink/?LinkId=62313)です。  
  
## <a name="publishing-schemas-that-specify-values-for-minoccurs-or-maxoccurs-attributes"></a>minOccurs 属性または maxOccurs 属性の値を指定するスキーマの公開  
 含むスキーマを発行する場合 **minOccurs** または **maxOccurs** 属性値を指定して、これらの値が公開された Web サービスによって公開されるスキーマで異なる場合があります。 一般的な経験則として、minOccurs 属性はすべて 0 (minOccurs=0) に変換され、maxOccurs 属性は 1 または unbounded (maxOccurs=1 または maxOccurs=unbounded) に変換されます。  
  
## <a name="publishing-envelope-schemas"></a>エンベロープ スキーマの公開  
 Web サービスとして公開するエンベロープ スキーマがある場合、生成される Web プロジェクトを手動で変更する必要があります。  
  
#### <a name="to-modify-the-generated-web-project-for-envelope-schemas"></a>エンベロープ スキーマの生成された Web プロジェクトを変更するには  
  
1.  <`myWebService`>.asmx.cs ファイルを開きます。  
  
2.  ファイルを編集し、`bodyTypeAssemblyQualifiedName = <dll.name.version.>` を `bodyTypeAssemblyQualifiedName = null` に変更します。  
  
> [!NOTE]
>  前の .dll ファイルが引き続き ASPNET ワーカー プロセス内にある場合、インターネット インフォメーション サービス (IIS) のリセットが必要になることがあります。  
  
## <a name="web-service-and-web-method-attributes"></a>Web サービス属性および Web メソッド属性  
 BizTalk Web サービス公開ウィザードでは、ASP.NET で使用する Web サービス属性または Web メソッド属性をカスタマイズできません。 一部の属性は、ウィザードで提供される情報に基づいて自動的に設定されます。 ウィザードはそれ以外の属性を使用しません。  
  
 BizTalk Web サービス公開ウィザードによって生成された Web サービスの既存の属性を変更したり、新しい属性を追加したりすると、Web サービスが正常に機能しなくなることがあります。  
  
 Web サービスおよび Web メソッド属性の詳細については、次を参照してください。、 **WebServiceAttribute** と **WebMethodAttribute** 、.NET Framework SDK ドキュメント内のクラスです。  
  
## <a name="web-method-required"></a>Web メソッドの必要性  
 Web サービスには、少なくとも 1 つの Web メソッドが必要です。 Web メソッドが 1 つもないと、作成された操作をポートの種類に設定できません。 XLANG/s は、操作が設定されていないポートの種類をサポートしません。  
  
## <a name="dbcs-character-support"></a>DBCS 文字のサポート  
 Web サービスは、中国語/日本語/韓国語 (CJK) の漢字拡張 A 文字をサポートしません。  
  
## <a name="republishing-web-services-using-the-biztalk-web-services-publishing-wizard"></a>BizTalk Web サービス公開ウィザードを使用した Web サービスの再公開  
 BizTalk Web サービス公開ウィザードを使用して、公開された Web サービスを再公開できます。 **Web * * * サービス * * * プロジェクト** 選択することができます ページで、 **上書き * * * Web * * * サービス** オプション。  
  
 ウィザードは、以前使用した設定を保存しません。 ウィザードを再実行するときに設定を変更すると、公開された Web サービスを使用する (呼び出す) Web クライアントは、動作に失敗する場合があります。 再公開された Web サービスを使用する (呼び出す) クライアントの Web 参照を更新する必要があります。  
  
## <a name="clients-of-published-web-services-may-not-receive-server-script-timeout-errors"></a>公開された Web サービスのクライアントがサーバー スクリプト タイムアウト エラーを受信しない  
 Web サービスで Web サービス公開ウィザードで生成された[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の既定のスクリプトのタイムアウト値で構成されて**110** (秒)。 これは、.NET Framework の **HttpServerUtility.ScriptTimeout** プロパティです。 .NET Framework を使用する web クライアントが要求のタイムアウト値に既定で構成されている **100** 秒です。 これは、.NET Framework の既定値 **HttpWebRequest.Timeout** プロパティです。  
  
 .NET framework を使用する Web クライアントが使用して生成された Web サービスを呼び出しているかどうか、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Web サービス公開ウィザード が既定ではまずクライアントの要求タイムアウトが発生するために、クライアントがサーバー スクリプト タイムアウト エラーを受信できないことです。 この問題を解決するには、次のいずれかの操作を実行します。  
  
-   値を増やすことでサーバー スクリプト タイムアウトよりも大きい値に、クライアント要求のタイムアウトを増やす、 **HttpWebRequest.Timeout** クライアントのプロパティです。  
  
-   値を減らすことにより、クライアント要求タイムアウトよりも小さい値にサーバー スクリプト タイムアウトを抑える、 **HttpServerUtility.ScriptTimeout** はサーバーのプロパティです。  
  
## <a name="see-also"></a>参照  
 [Web サービスの公開](../core/publishing-web-services.md)