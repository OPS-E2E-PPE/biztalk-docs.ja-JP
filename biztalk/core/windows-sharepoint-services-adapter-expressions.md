---
title: Windows SharePoint Services アダプターの式 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- macros, Windows SharePoint Services adapters
- configuring [Windows SharePoint Services adapters], supported macros
- configuring [Windows SharePoint Services adapters], expressions
- Windows SharePoint Services adapters, expressions
ms.assetid: 15e3afb2-0ef8-41b4-b3ec-de84af738c12
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 377859a1b2c28774342c6ff9dc5cc312c9fd82d9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973888"
---
# <a name="windows-sharepoint-services-adapter-expressions"></a>Windows SharePoint Services アダプターの式
このトピックは、形式との値として指定できる文字列の意味について説明します、**ファイル NameProperty ソース**Windows SharePoint Services アダプターのプロパティです。 関連するコンテキスト プロパティについても説明**WSS です。Filename**と**WSS です。ConfigPropertiesXml**です。 これらの式を使用すると、メッセージや BizTalk システムから抽出された値だけでなく、ファイル名の値、つまり、カスタム Windows SharePoint Service 列値を、リテラルに基づいて簡単に定義できます。  
  
 式には、リテラルやマクロを含めることができます。 リテラルは、入力したとおりにファイル名に表示されます。 マクロは、'%' 文字の間に配置する必要があります。 マクロの例として `%MessageID%` があります。このマクロは、実行時にメッセージの GUID に置き換えられます。  
  
> [!NOTE]
>  使用する場合、% 文字がリテラルとして、または、XPATH 内で、次のようにエスケープする必要がある\\% です。 1 つの % はマクロの区切り記号と見なされます場所、 \\% は 1 つの % によって実行時に置き換えられます。 \ 文字は、次のようにエスケープする必要があります\\\\です。  
  
## <a name="expression-examples"></a>式の例  
  
|デザイン時の値|実行時の値|  
|-----------------------|-------------------|  
|XYZ 社|XYZ 社|  
|PurchaseOrder|PurchaseOrder|  
|%MessageID%|55B93F27-7455-4066-ABE1-B4EBE6839A1A|  
|PurchaseOrder - %MessageID%|PurchaseOrder - 55B93F27-7455-4066-ABE1-B4EBE6839A1A|  
|割引\\%10|Discount %10|  
|PurchaseOrder - %XPATH=//ns0:PurchaseOrder/ns0:ID%|PurchaseOrder – 10001|  
|PurchaseOrder - %XPATH=//ns0:PurchaseOrder/ns0:PartnerName%-%XPATH=//ns0:PurchaseOrder/ns0:ID%|PurchaseOrder – Contoso-10001|  
  
## <a name="supported-macros"></a>サポートされているマクロ  
  
|デザイン時の値|実行時の値|  
|-----------------------|-------------------|  
|%MessageID%|一意な GUID を表す BizTalk メッセージ ID。|  
|%SendingOrchestrationID%|メッセージの発信元であるオーケストレーション インスタンスの BizTalk ID。|  
|%SendingOrchestrationType%|メッセージの発信元であるオーケストレーションの種類名。|  
|%Xpath =\<xpath\>%|メッセージから値を抽出する際に XPATH を使用するように指定できます。 "\<xpath\>"有効な XPATH 式と置き換える必要があります。 **注:** ' Namespace Aliases' または WSS 内の式の外部名前空間の別名を定義する必要があります。ConfigNamespaceAliases フィールドです。|  
|%Filename%|メッセージのコンテキスト プロパティ WSS.Filename から抽出されたファイル名の値と置き換えられます。 SharePoint から受け取ったメッセージの WSS.Filename コンテキスト プロパティの値には、SharePoint ファイル名が設定されます。 戻り値は、Path.GetFilenameWithoutExtension を使用して前処理されます。 **注:** WSS でこのマクロは使用できません。Config * (オーケストレーション) からコンテキスト プロパティです。|  
|%Extension%|メッセージのコンテンツ プロパティ WSS.Filename から抽出されたファイル拡張子の値に置き換えられます。 SharePoint から受け取ったメッセージの WSS.Filename コンテキスト プロパティの値には、SharePoint ファイル名が設定されます。 戻り値は、Path.GetExtension を使用して前処理されます。 戻り値には、"." は含まれません。 **注:** WSS でこのマクロは使用できません。Config * (オーケストレーション) からコンテキスト プロパティです。|  
  
 プロパティの昇格でサポートされている有効な式は、デザイン時の有効なファイル名です。 デザイン時のファイル名は、実行時に、Windows SharePoint Services ファイル名に拡張されます。 この Windows SharePoint Services ファイル名には、次のようにいくつかの制限事項があります。  
  
-   有効な Windows ファイル名には、Unicode 文字を含めることができます。  < > & #124 です。 "# {} % & ~ およびタブ文字や複数の期間。  
  
-   ファイル名は 256 文字以下にしてください。また、URL 全体は 256 文字以下にする必要があります。  
  
-   拡張された Windows SharePoint Services ファイル名に無効な文字が含まれている場合、または拡張されたファイル名や URL が長すぎる場合は、エラーがアプリケーション イベント ログに記録され、メッセージは中断されます。 [グループ ハブ] ページでは、メッセージ イベントおよびサービス インスタンスの追跡を使用して、エラーおよびメッセージの状態を表示することもできます。  
  
## <a name="see-also"></a>参照  
 [サービスの受信場所を Windows SharePoint を構成する方法](../core/how-to-configure-a-windows-sharepoint-services-receive-location.md)   
 [Windows SharePoint Services 送信ハンドラーを構成する方法](../core/how-to-configure-a-windows-sharepoint-services-send-handler.md)   
 [Windows SharePoint Services 送信ポートを構成する方法](../core/how-to-configure-a-windows-sharepoint-services-send-port.md)   
 [Windows SharePoint Services アダプターのプロパティのリファレンス](../core/windows-sharepoint-services-adapter-properties-reference.md)   
 [サポートされている Windows SharePoint Services 列の型](../core/supported-windows-sharepoint-services-column-types.md)