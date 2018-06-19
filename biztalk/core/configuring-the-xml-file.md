---
title: XML ファイルの構成 |Microsoft ドキュメント
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
ms.openlocfilehash: 4d791de9b6fe90ebb850874026e8d52e49732f32
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233826"
---
# <a name="configuring-the-xml-file"></a>XML ファイルの構成
エンタープライズ シングル サインオン (SSO) をインストールすると、ENTSSO.xml という XML ファイルが Extensions ディレクトリにインストールされます。 このファイルを編集することにより、ENTSSO 管理エージェント (MA) のすべてのインスタンスに適用される構成を定義できます。  
  
 このファイルは、次のような内容で構成されています。  
  
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
  
## <a name="xml-elements-and-attributes"></a>XML 要素と XML 属性  
 次の一覧は、この XML ファイルで定義する要素と属性について説明したものです。 このファイル内のすべての要素名と属性名では、小文字と大文字が区別されます。  
  
 **要素: ENTSSO** -単一の ENTSSO MA インスタンスの構成を定義します。 複数の ENTSSO 要素は使用できません。  
  
 **属性: 名前**- ENTSSO 管理エージェントのインスタンスの名前を定義し、Microsoft Identity Integration Server (MIIS) の ENTSSO 管理エージェント インスタンスの名前に一致する必要があります。  
  
 **属性: adma** -この ENTSSO 管理エージェント インスタンスによって使用される Active Directory 管理エージェントのインスタンスの名前を定義します。 Active Directory 管理エージェントでは、マッピング用の Windows ドメイン名と Windows ユーザー名が提供されます。 この Active Directory 管理マネージャ インスタンスの名前は、MIIS の Active Directory 管理エージェント インスタンスの名前と一致している必要があります。  
  
 **属性: deleteAll** - 省略可能です。 既定値は`true`します。 これを `true` に設定し、Windows ID を削除すると、すべての ENTSSO アプリケーションから、その Windows ID とのマッピングがすべて削除されます。  
  
 **要素: アプリケーション**-SSO 関連アプリケーションと外部管理エージェントの間のリレーションシップを定義します。 複数の `Application` 要素を使用できます。  
  
 **属性: 名前**-SSO 関連アプリケーションの名前を定義します。 このアプリケーションは、ENTSSO システム内に既に存在している必要があります。  
  
 **属性: sourceMA** -ソース (外部) のインスタンス名を定義します。 このアプリケーションのマッピングの外部 UserId を提供するために使用する管理エージェント。 この外部管理エージェント インスタンスの名前は、MIIS の外部 MA インスタンスの名前と一致している必要があります。  
  
 **属性: 作成**- 省略可能です。 既定値は`true`します。 このアプリケーションのマッピングを作成するかどうかを定義します。  
  
 **属性: 削除**- 省略可能です。 既定値は`true`します。 このアプリケーションのマッピングを削除するかどうかを定義します。  
  
 **要素: SourceMA** - 省略可能です。 特定のソース (外部) 管理エージェント インスタンスのオブジェクト型と属性名を示します。 特定の管理エージェントに関するこの要素がない場合は、既定のオブジェクト型 ("person") と属性名 ("uid") が使用されます。 複数の `SourceMA` 要素を使用できます。  
  
 **属性: 名前**-ソース (外部) の名前の管理エージェント。 この名前は、`sourceMA` 要素の `Application` 属性の名前の少なくとも 1 つと一致している必要があります。  
  
 **属性: objectType** - 省略可能です。 既定値は`person`します。 外部 UserId を提供する管理エージェントのオブジェクト型名が `person` でない場合は、ここで指定する必要があります。  
  
 **属性: 属性の**- 省略可能です。 既定値は`uid`します。 外部 UserId を提供する管理エージェントの属性名が `uid` でない場合は、ここで指定できます。  
  
## <a name="see-also"></a>参照  
 [ENTSSO 管理エージェントを使用する方法](../core/how-to-use-the-entsso-management-agent.md)