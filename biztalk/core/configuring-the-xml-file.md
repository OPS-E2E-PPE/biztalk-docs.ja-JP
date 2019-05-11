---
title: XML ファイルの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 52851901-8374-412f-9c29-83845d8d4861
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a41fdd9689f822736607ecbc7ec1ea0f0fd4f36c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355059"
---
# <a name="configuring-the-xml-file"></a>XML ファイルを構成します。
エンタープライズ シングル サインオン (SSO) をインストールするときに ENTSSO.xml という XML ファイルが Extensions ディレクトリにインストールされています。 ファイルを編集するには、ENTSSO 管理エージェント (MA) のすべてのインスタンスの構成を定義します。  
  
 ファイルは、次のような。  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<sso>  
  
  <SourceMA name="RACFMA1" objectType="person" attribute="uid"/>  
  <SourceMA name="ACF2" objectType="person" attribute="uid"/>  
  
  <ENTSSOMA name ="ENTSSOMA1" adma="ADMA1" deleteAll="true">  
    <Application name="AppForRACF1A" sourceMA="RACFMA1" create="true" delete="true"/>  
    <Application name="AppForRACF1B" sourceMA="RACFMA1" create="true" delete="false"/>  
  </ENTSSOMA>  
  
  <ENTSSOMA name ="ENTSSOMA2" adma="ADMA1" deleteAll="true">  
    <Application name="AppForACF2" sourceMA="ACF2"/>  
  </ENTSSOMA>  
  
</sso>  
```  
  
## <a name="xml-elements-and-attributes"></a>XML 要素と属性  
 次の一覧には、要素と XML ファイルで定義する属性について説明します。 このファイル内のすべての要素と属性名は大文字小文字が区別ことに注意してください。  
  
 **要素:ENTSSO** -単一の ENTSSO MA インスタンスの構成を定義します。 複数の ENTSSO 要素が許可されます。  
  
 **属性: 名前**-、ENTSSO 管理エージェントのインスタンスの名前を定義し、Microsoft Identity Integration Server (MIIS) の ENTSSO 管理エージェント インスタンスの名前に一致する必要があります。  
  
 **属性: adma** -この ENTSSO 管理エージェント インスタンスによって使用される Active Directory 管理エージェントのインスタンスの名前を定義します。 Active Directory 管理エージェントは、Windows ドメイン名と Windows ユーザー名マッピングを提供します。 この Active Directory 管理エージェント インスタンスの名前は、MIIS の Active Directory 管理エージェント インスタンスの名前と一致する必要があります。  
  
 **属性: deleteAll** - 省略可能です。 既定値は`true`します。 設定されている場合`true`、および、Windows id を削除すると、その Windows id を持つすべてのマッピングは、すべての ENTSSO アプリケーションから削除されます。  
  
 **要素:アプリケーション**-SSO 関連アプリケーションと外部管理エージェント間のリレーションシップを定義します。 複数`Application`要素を使用します。  
  
 **属性: 名前**-SSO 関連アプリケーションの名前を定義します。 このアプリケーションは、ENTSSO システム内で既に存在する必要があります。  
  
 **属性: sourceMA** -ソース (外部) のインスタンス名を定義します。 このアプリケーションのマッピングの外部 UserId を提供するために使用する管理エージェント。 この外部管理エージェント インスタンスの名前は、MIIS の外部 MA インスタンスの名前と一致する必要があります。  
  
 **属性: 作成**- 省略可能です。 既定値は`true`します。 このアプリケーションのマッピングを作成するかどうかを定義します。  
  
 **属性: 削除**- 省略可能です。 既定値は`true`します。 このアプリケーションのマッピングを削除するかどうかを定義します。  
  
 **要素:SourceMA** - 省略可能。 特定のソース (外部) 管理エージェント インスタンスのオブジェクトの種類と属性名を識別します。 この要素が特定の管理エージェントの存在しない場合、既定のオブジェクト型 ("person") と属性名 ("uid") と見なされます。 複数`SourceMA`要素を使用します。  
  
 **属性: 名前**-ソース (外部) の名前の管理エージェント。 この名前には、少なくとも 1 つの一致する必要があります、`sourceMA`属性の名前、`Application`要素。  
  
 **属性: objectType** - 省略可能です。 既定値は`person`します。 外部 UserId を提供するオブジェクトの型名がない`person`、ここで指定する必要があります。  
  
 **属性: 属性の**- 省略可能です。 既定値は`uid`します。 外部 UserId を提供する属性名がない`uid`、ここで指定できます。  
  
## <a name="see-also"></a>参照  
 [ENTSSO 管理エージェントを使用する方法](../core/how-to-use-the-entsso-management-agent.md)