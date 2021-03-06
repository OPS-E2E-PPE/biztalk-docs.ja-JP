---
title: インスタンス データの検証 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 19c3ca83-0abf-42ba-8e29-653ff12d5e20
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 648e3e97a3a7173278256d109f362938c3176988
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398586"
---
# <a name="validate-instance-data"></a>インスタンス データを検証します。

## <a name="overview"></a>概要
マップのテストを実行している際に、インスタンス データを送信元および送信先スキーマに照合して検証し、スキーマの構造に準拠していることを確認したい場合があります。 送信元または送信先スキーマに対してインスタンス メッセージを検証するには、ソリューション エクスプ ローラーでスキーマを右クリックし、**インスタンスの検証**です。  

> [!IMPORTANT]
>  出力でカスタム データまたは定数を使用する場合、送信元のテスト データと送信先の定数値のデータ型が有効であることを確認する必要があります。 マップを検証するときに BizTalk マッパーには、インスタンス データに、スキーマによって定義されたすべてのデータ型に違反しているかどうかはチェックされません。 データ型の確認は、マップのテストまたはインスタンス データの検証を行うと実行されます。  

 生成し、BizTalk エディターを使用してインスタンス データを検証する方法の詳細については、次を参照してください。[インスタンス メッセージの生成と検証](../core/instance-message-generation-and-validation.md)と[インスタンスの検証](../core/instance-validation.md)です。 . **値**BizTalk がインスタンス データがどのように生成するか、スキーマのノードのプロパティにも影響します。 詳細については、次を参照してください。、**スキーマのノード プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。

## <a name="see-also"></a>参照  
- [インスタンス メッセージの生成および検証](../core/instance-message-generation-and-validation.md)   
- [Visual Studio でのスキーマを検証する方法](../core/how-to-validate-schemas-in-visual-studio.md)   
- **マップ プロパティのリファレンス** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]  
- [マップのテスト](../core/testing-maps.md)
