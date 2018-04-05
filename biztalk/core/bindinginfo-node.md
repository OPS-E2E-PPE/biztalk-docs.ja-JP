---
title: BindingInfo ノード |Microsoft ドキュメント
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
ms.openlocfilehash: 3dc15cbfe4bb3a98e17a894c5a763c0ca18bdcb3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="bindinginfo-node"></a>BindingInfo ノード
**BindingInfo**バインド ファイルのノードは、バインド ファイルのルート ノードと、バインド ファイル内のエントリのすべてに適用される情報だけでなく、バインド ファイルがエクスポートされた BizTalk Server に関する情報が含まれています差出人。  
  
## <a name="nodes-in-the-bindinginfo-node"></a>BindingInfo ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノード型**|**データ型**|**Description**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|アセンブリ|属性|xs:string|バインド ファイル作成時に使用される Microsoft.BizTalk.Deployment dll の情報を指定します。 このアセンブリの Version、Culture、PublicKeyToken の各属性をコンマで区切って記述します。|必須|既定値: **"Microsoft.BizTalk.Deployment, Version =, Culture = neutral, PublicKeyToken = 31bf3856ad364e35"**|  
|バージョン|属性|xs:string|バインド ファイルが生成された BizTalk Server のバージョンを指定します。|必須|既定値: **3.5.1.0**|  
|BindingStatus|属性|BindingState (SimpleType)|バインド ファイルと共にエクスポートされたアイテムのバインド状態を指定します。|必須|既定値: なし<br /><br /> 有効な値:<br /><br /> -不明<br />-NoBindings<br />バインドされていません。<br />-PartiallyBound<br />-FullyBound|  
|BoundEndpoints|属性|xs:int|バインド ファイル内のバインドされたエンドポイントの数を指定します。|必須|既定値: **0**|  
|TotalEndpoints|属性|xs:int|バインド ファイル内のエンドポイントの合計数を指定します。|必須|既定値: **0**|  
|Description|要素|xs:string|バインド ファイルの BindingInfo セクションの説明テキストを指定します。|任意|既定値: 空|  
|Timestamp|要素|xs:dateTime|バインド ファイルがエクスポートされた日時を指定します。|必須|既定値: バインド ファイルがエクスポートされたときの BizTalk Server での時刻。|  
|[ModuleRefCollection ノード](../core/modulerefcollection-node.md)|レコード|ArrayOfModuleRef (ComplexType)|バインド ファイルと共にエクスポートされた .NET アセンブリのコンテナー ノードです。|任意|既定値: なし|  
|[SendPortCollection ノード](../core/sendportcollection-node.md)|レコード|ArrayOfSendPort (ComplexType)|バインド ファイルと共にエクスポートされた送信ポートのコンテナー ノードです。|任意|既定値: なし|  
|[DistributionListCollection ノード](../core/distributionlistcollection-node.md)|レコード|ArrayOfDistributionList (ComplexType)|バインド ファイルと共にエクスポートされた同報リストのコンテナー ノードです。|任意|既定値: なし|  
|[ReceivePortCollection ノード](../core/receiveportcollection-node.md)|レコード|ArrayOfReceivePort (ComplexType)|バインド ファイルと共にエクスポートされた受信ポートのコンテナー ノードです。|任意|既定値: なし|  
  
 次のコード例は、バインド ファイルの BindingInfo ノードで使用される XML の形式を示しています。  
  
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