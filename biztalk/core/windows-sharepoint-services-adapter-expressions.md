---
title: Windows SharePoint Services アダプターの式 |Microsoft Docs
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
ms.openlocfilehash: 553ed4526607a30141f9643f08a5afa11c5bc538
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65240333"
---
# <a name="windows-sharepoint-services-adapter-expressions"></a>Windows SharePoint Services アダプターの式
このトピックでは、形式との値として指定できる文字列の意味について説明します、**ファイル NameProperty ソース**Windows SharePoint Services アダプターのプロパティ。 関連するコンテキストのプロパティについても説明**WSS。ファイル名**と**WSS。ConfigPropertiesXml**します。 これらの式を使用すると、ファイル名の値、またはリテラルと、メッセージや BizTalk システムから抽出された値に基づいて、カスタムの Windows SharePoint Service 列値を簡単に定義できます。  
  
 式には、リテラルやマクロを含めることができます。 それらを入力したとおりに、リテラルがファイル名で表示されます。 マクロは、'%' 文字の間に配置する必要があります。 マクロの例は`%MessageID%`ランタイムでは、メッセージの GUID に置き換えられます。  
  
> [!NOTE]
>  % 文字をリテラルとして、または、XPATH 内で使用する場合、次のようにはエスケープする必要があります\\%。 単一の % はマクロの区切り記号、考慮する場所、\\単一の % で、実行時に % が置き換えられます。 \ 文字は、次のようにエスケープする必要があります\\\\します。  
  
## <a name="expression-examples"></a>式の例  
  
|デザイン時の値|ランタイム値|  
|-----------------------|-------------------|  
|XYZ 社|XYZ 社|  
|PurchaseOrder|PurchaseOrder|  
|%MessageID%|55B93F27-7455-4066-ABE1-B4EBE6839A1A|  
|PurchaseOrder の %messageid%|PurchaseOrder - 55B93F27-7455-4066-ABE1-B4EBE6839A1A|  
|割引\\10%|10% を割引します。|  
|PurchaseOrder - %XPATH=//ns0:PurchaseOrder/ns0:ID%|PurchaseOrder – 10001|  
|PurchaseOrder - %XPATH=//ns0:PurchaseOrder/ns0:PartnerName%-%XPATH=//ns0:PurchaseOrder/ns0:ID%|PurchaseOrder – Contoso 10001|  
  
## <a name="supported-macros"></a>サポートされているマクロ  
  
|デザイン時の値|ランタイム値|  
|-----------------------|-------------------|  
|%MessageID%|これは一意の GUID を BizTalk メッセージの ID です。|  
|%Sendingorchestrationid%|メッセージが発信元であるオーケストレーション インスタンスの BizTalk ID。|  
|%SendingOrchestrationType%|メッセージが発信元であるオーケストレーションの型名。|  
|%Xpath =\<xpath\>%|メッセージから値を抽出するために使用される XPATH を指定できます。 "\<xpath\>"有効な XPATH 式に置き換える必要があります。 **注:**' Namespace Aliases' または WSS の式の外部名前空間の別名を定義する必要があります。ConfigNamespaceAliases フィールドです。|  
|ファイル名 %|WSS メッセージ コンテキスト プロパティから抽出されたファイル名の値に置き換えられます。ファイル名。 SharePoint から受信したメッセージは、WSS があります。ファイル名のコンテキスト プロパティの値は、SharePoint ファイルの名前に設定します。 返される値は Path.GetFilenameWithoutExtension を使用して前処理されます。 **注:** このマクロは、WSS では使用できません。Config * (オーケストレーション) からコンテキスト プロパティです。|  
|拡張機能 %|WSS メッセージ コンテキスト プロパティから抽出するファイルの拡張機能値に置き換えられます。ファイル名。 SharePoint から受信したメッセージは、WSS があります。ファイル名のコンテキスト プロパティの値は、SharePoint ファイルの名前に設定します。 返される値は Path.GetExtension を使用して前処理されます。 返される値にが含まれていません"."です。 **注:** このマクロは、WSS では使用できません。Config * (オーケストレーション) からコンテキスト プロパティです。|  
  
 プロパティの昇格でサポートされている任意の有効な式は、有効なデザイン時のファイル名です。 デザイン時のファイル名は、Windows SharePoint Services ファイル名に、実行時に展開されます。 この Windows SharePoint Services ファイル名には、次のように説明されているいくつか追加の制限があります。  
  
-   有効な Windows ファイル名は、次を除く任意の Unicode 文字を含めることができます:/\: *?  < > &#124; "# {} % & ~ およびタブ文字や複数の期間。  
  
-   ファイル名は 256 文字より長くすることはできませんし、URL 全体は 256 文字以下である必要があります。  
  
-   展開の Windows SharePoint Services ファイル名に無効な文字が含まれている場合、または拡張されたファイルの名前または URL が長すぎる場合は、アプリケーション イベント ログでエラーがログに記録して、メッセージは中断されます。 エラーおよびメッセージの状態も表示されます、グループ ハブ ページで、メッセージ イベントおよびサービス インスタンスの追跡を使用します。  
  
## <a name="see-also"></a>参照  
 [サービスの受信場所を Windows SharePoint を構成する方法](../core/how-to-configure-a-windows-sharepoint-services-receive-location.md)   
 [Windows SharePoint Services 送信ハンドラーを構成する方法](../core/how-to-configure-a-windows-sharepoint-services-send-handler.md)   
 [Windows SharePoint Services 送信ポートを構成する方法](../core/how-to-configure-a-windows-sharepoint-services-send-port.md)   
 [Windows SharePoint Services アダプターのプロパティに関するリファレンス](../core/windows-sharepoint-services-adapter-properties-reference.md)   
 [サポートされている Windows SharePoint Services 列の型](../core/supported-windows-sharepoint-services-column-types.md)