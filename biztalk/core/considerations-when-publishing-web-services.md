---
title: Web サービスの発行時の考慮事項 |Microsoft Docs
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
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72d45e269d091c2c39b44e260c10a96a3895706e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390336"
---
# <a name="considerations-when-publishing-web-services"></a>Web サービスを公開する際の考慮事項
このトピックでは、情報を提供します。 Web サービスを発行する前に考慮する必要があります。  
  
## <a name="publishing-schemas-and-the-include-element"></a>発行のスキーマおよび include 要素  
 いくつかのシナリオがある場所が含まれたスキーマ、**含める**要素は、Web サービスとして発行できません。 BizTalk Web サービス公開ウィザードを完了すると、エラーが発生します。 これらの制限事項を以下に示します。  
  
- 循環が含まれています (インクルードされるスキーマが、**含める**をインクルードするスキーマの要素)  
  
- 未解決**schemaLocation**属性には、エラーが発生  
  
  制限の詳細については要素が含まれてに「含める要素のバインディング サポート」を参照してください[ http://go.microsoft.com/fwlink/?LinkId=62312](http://go.microsoft.com/fwlink/?LinkId=62312)します。  
  
## <a name="publishing-schemas-and-the-import-element"></a>発行のスキーマおよび import 要素  
 BizTalk Web サービス公開ウィザードは、.NET Framework に付属する XSD.exe と同じ制限です。 詳細についてで「Import 要素のバインディング サポート」を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=62311](http://go.microsoft.com/fwlink/?LinkId=62311)します。  
  
## <a name="publishing-schemas-and-the-redefine-element"></a>発行のスキーマおよび redefine 要素  
 BizTalk Web サービス公開ウィザードは、.NET Framework に付属する XSD.exe と同じ制限です。 詳細についてで「Redefine 要素バインディング サポート」を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=62313](http://go.microsoft.com/fwlink/?LinkId=62313)します。  
  
## <a name="publishing-schemas-that-specify-values-for-minoccurs-or-maxoccurs-attributes"></a>MinOccurs または maxOccurs 属性の値を指定するスキーマの公開  
 含むスキーマを発行する場合**minOccurs**または**maxOccurs**属性値を指定して、これらの値が公開された Web サービスによって公開されるスキーマで異なる場合があります。 一般則として、minOccurs のすべての属性が 0 に変換されます (minOccurs = 0) および maxOccurs 属性が 1 に変換または unbounded (maxOccurs = 1 または maxOccurs = unbounded)。  
  
## <a name="publishing-envelope-schemas"></a>エンベロープ スキーマの公開  
 Web サービスとして公開するエンベロープ スキーマがあれば、手動で生成された Web プロジェクトを変更する必要があります。  
  
#### <a name="to-modify-the-generated-web-project-for-envelope-schemas"></a>エンベロープ スキーマの生成された Web プロジェクトを変更するには  
  
1.  開いている、<`myWebService`>. ある asmx.cs ファイル。  
  
2.  ファイルを編集し、変更`bodyTypeAssemblyQualifiedName = <dll.name.version.>`に`bodyTypeAssemblyQualifiedName = null`します。  
  
> [!NOTE]
>  以前の .dll ファイルが引き続き ASPNET ワーカー プロセスの場合は、インターネット インフォメーション サービス (IIS) をリセットする必要があります。  
  
## <a name="web-service-and-web-method-attributes"></a>Web サービスおよび Web メソッド属性  
 BizTalk Web サービス公開ウィザードでは、Web サービスまたは ASP.NET で使用する Web メソッド属性をカスタマイズできません。 いくつかの属性は、ウィザードによって提供される情報に基づいて自動的に設定されます。 ウィザードでは、その他の属性は使用しません。  
  
 既存の属性を変更または BizTalk Web サービス公開ウィザードが生成する Web サービスに新しい属性を追加するには、正しく機能する Web サービスがある場合があります。  
  
 Web サービスと Web メソッド属性の詳細については、次を参照してください。、 **WebServiceAttribute**と**WebMethodAttribute** 、.NET Framework SDK ドキュメント内のクラス。  
  
## <a name="web-method-required"></a>必要な web メソッド  
 Web サービスを少なくとも 1 つの Web メソッドが必要です。 少なくとも 1 つの Web メソッドを使用しないでポートの種類を作成、操作する必要はありません。 XLANG/秒は、操作がないポートの種類をサポートしていません。  
  
## <a name="dbcs-character-support"></a>DBCS 文字のサポート  
 Web サービスは、中国語/日本語/韓国語 (CJK) 統合漢字拡張 A 文字をサポートしていません。  
  
## <a name="republishing-web-services-using-the-biztalk-web-services-publishing-wizard"></a>BizTalk Web サービス公開ウィザードを使用して Web サービスを再パブリッシュ  
 BizTalk Web サービス公開ウィザードを使用して、公開済み Web サービスを再発行することができます。 **Web**<strong>サービス</strong>**プロジェクト**ページで、選択できる、**上書き**<strong>Web</strong> **サービス**オプション。  
  
 ウィザードでは以前に使用されるストアの設定ではなく、します。 ウィザードを再実行するときに、設定の変更を行った場合、使用する (呼び出す) Web クライアント公開された Web サービスがあります。 再公開 Web サービス (呼び出し) を使用するすべてのクライアントの Web 参照を更新する必要があります。  
  
## <a name="clients-of-published-web-services-may-not-receive-server-script-timeout-errors"></a>公開済み Web サービスのクライアントは、サーバー スクリプト タイムアウト エラーを受信しない可能性があります。  
 Web サービスで Web サービス公開ウィザードで生成された[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]既定のスクリプトのタイムアウト値で構成が**110**秒。 これは、.NET Framework の既定値です。 **HttpServerUtility.ScriptTimeout**プロパティ。 .NET Framework を使用する web クライアントが要求のタイムアウト値では既定で構成されている**100**秒。 これは、.NET Framework の既定値**HttpWebRequest.Timeout**プロパティ。  
  
 .NET framework を使用する Web クライアントが使用して生成された Web サービスを呼び出しているかどうか、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Web サービスの公開ウィザードでは、既定ではまずクライアントの要求タイムアウトが発生するために、クライアントがサーバー スクリプト タイムアウト エラーを受信できないことができます。 この問題を解決するには、次のいずれかの操作を実行します。  
  
-   値を増やすことで、サーバー スクリプト タイムアウトよりも大きい値にクライアント要求タイムアウトの値を増やし、 **HttpWebRequest.Timeout**クライアントのプロパティ。  
  
-   値を減らすことで、クライアント要求のタイムアウトよりも小さい値に、サーバー スクリプト タイムアウトを減らす、 **HttpServerUtility.ScriptTimeout**サーバーのプロパティ。  
  
## <a name="see-also"></a>参照  
 [Web サービスの公開](../core/publishing-web-services.md)