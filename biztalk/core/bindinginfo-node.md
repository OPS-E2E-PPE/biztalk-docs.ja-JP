---
title: BindingInfo ノード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BindingInfo node [binding file]
ms.assetid: a71d100c-cf8b-4a54-b239-ee0ca2d8148c
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73b76ab4e4b40b89676dbe40b5759b4400308ceb
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528310"
---
# <a name="bindinginfo-node"></a>BindingInfo ノード
**BindingInfo**バインド ファイルのノードがバインド ファイルのルート ノードと、バインド ファイル内のエントリのすべてに適用される情報に加えて、バインド ファイルがエクスポートされたこと、BizTalk Server に関する情報が含まれます差出人。  
  
## <a name="nodes-in-the-bindinginfo-node"></a>BindingInfo ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノードの種類**|**[データ型]**|**[説明]**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|アセンブリ|属性|xs:string|バインド ファイルを作成するときに使用される Microsoft.BizTalk.Deployment dll の情報を指定します。 このアセンブリのコンマ区切りのバージョン、カルチャ、および PublicKeyToken の属性が含まれています。|必須|既定値:**"Microsoft.BizTalk.Deployment, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"**|  
|バージョン|属性|xs:string|BizTalk Server で生成されたバインド ファイルのバージョンを指定します。|必須|既定値:**3.5.1.0**|  
|BindingStatus|属性|BindingState (SimpleType)|バインド ファイルと共にエクスポートされたアイテムのバインドの状態を指定します。|必須|既定値:なし<br /><br /> 有効な値:<br /><br /> -不明<br />-NoBindings<br />バインドされていません。<br />-PartiallyBound<br />-   FullyBound|  
|BoundEndpoints|属性|xs:int|バインド ファイルにバインドされているエンドポイントの数を指定します。|必須|既定値:**0**|  
|TotalEndpoints|属性|xs:int|バインド ファイルでは、エンドポイントの合計数を指定します。|必須|既定値:**0**|  
|説明|要素|xs:string|バインド ファイルの BindingInfo セクションの説明テキストを指定します。|任意|既定値: 空|  
|Timestamp|要素|xs:dateTime|バインド ファイルがエクスポートされたを指定します。|必須|既定値:バインド ファイルのエクスポート時に、BizTalk server の時間。|  
|[ModuleRefCollection ノード](../core/modulerefcollection-node.md)|レコード|ArrayOfModuleRef (ComplexType)|バインド ファイルと共にエクスポートされた .NET アセンブリのコンテナー ノードです。|任意|既定値: なし|  
|[SendPortCollection ノード](../core/sendportcollection-node.md)|レコード|ArrayOfSendPort (ComplexType)|送信ポートのコンテナー ノードは、バインド ファイルと共にエクスポートします。|任意|既定値: なし|  
|[DistributionListCollection ノード](../core/distributionlistcollection-node.md)|レコード|ArrayOfDistributionList (ComplexType)|バインド ファイルと共にエクスポートされた同報リストのコンテナー ノードです。|任意|既定値: なし|  
|[ReceivePortCollection ノード](../core/receiveportcollection-node.md)|レコード|ArrayOfReceivePort (ComplexType)|バインド ファイルと共にエクスポートされる受信ポートのコンテナー ノードです。|任意|既定値: なし|  
  
 次のコードでは、バインド ファイルの BindingInfo ノードで使用される XML の形式を示します。  
  
```  
<BindingInfo xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
Assembly="Microsoft.BizTalk.Deployment, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"   
Version="3.5.1.0" BindingStatus="FullyBound"   
BoundEndpoints="12"   
TotalEndpoints="12">  
<Description/>  
<Timestamp>2005-08-23T16:27:40.5948205-07:00</Timestamp>  
```  
  
## <a name="see-also"></a>参照  
 [バインド ファイルのカスタマイズ](../core/customizing-binding-files.md)