---
title: LOBApplication |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- trading partners, submitting actions
- LOBs, submitting actions
- LOBApplication utility
- trading partners, response messages
- LOBs, LOBApplication utility
- LOBs, response messages
ms.assetid: ad5986af-4175-49cd-806b-04e1fde63f55
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc9859e210036806cebcd76f63235d47ca972976
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978579"
---
# <a name="lobapplication"></a>LOBApplication
実際の基幹業務 (LOB) デスクトップ プログラムをシミュレートして、アクション メッセージまたは応答メッセージを取引先に送信するには、LOBApplication ユーティリティを使用します。  
  
 Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]サンプル メッセージを提供します、 \<*ドライブ*\>\Program Files (x86) \Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\LOBApplication\SampleInstances フォルダーです。  
  
## <a name="location-in-sdk"></a>SDK でのパス  
 \<*ドライブ*\>\Program Files (x86) \Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\lobapplication  
  
## <a name="running-lobapplication"></a>LOBApplication の実行  
  
#### <a name="to-run-lobapplication"></a>LOBApplication を実行するには  
  
1.  Windows エクスプ ローラーで、移動\<*ドライブ*\>\Program Files (x86) \Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\\します。  
  
2.  ダブルクリック**LOBApplication.exe**、し、ENTER キーを押します。  
  
     ユーティリティの実行に必要な情報を入力するためのページが表示されます。  
  
## <a name="syntax-for-lobapplication"></a>LOBApplication の構文  
 使用して、 **LOB Application**ページをホームとパートナーの名前、プロセス PIP (Partner Interface) のプロパティ、および LOBApplication ユーティリティによって送信されたメッセージのメッセージのプロパティを指定します。  
  
 次の表に、各フィールドの使用方法、 **LOB Application**ページ。  
  
|プロパティ|目的|  
|--------------|----------------|  
|**Home Profile Name**|ホーム組織 (送信元パーティ) の名前を入力します。|  
|**取引先名**|取引先 (送信先パーティ) の名前を入力します。|  
|**PIP の名前**|入力の種類」などの PIP 表示コード**3 a 2**します。 この値は、大文字と小文字が区別されます。|  
|**[PIP Version]**|入力の種類」などの PIP のバージョン**V02.00**します。 この値は、大文字と小文字が区別されます。|  
|**PIP インスタンス ID** (省略可能)|たとえば、入力、PIP の英数字のインスタンス ID を入力**STD_3A2_V02.02**します。 特殊文字は使用しないでください。 この ID は取引先および PIP コードごとに固有でなければなりません。 アクション メッセージとしてマークされたメッセージのインスタンス ID が空白の場合、LOBApplication ユーティリティでは、自動的に生成された HUID 値が PIP インスタンス ID として使用されます。 **注:** を選択すると**応答**で、**メッセージ カテゴリ**、PIP インスタンス ID は、このフィールドに入力する必要があります。|  
|**[ファイル名]**|省略記号 ([...]) ボタンをクリックし、PIP インスタンス ファイルが保存されているフォルダーに移動して、PIP インスタンス ファイルをクリックします。|  
|**メッセージのカテゴリ**|メッセージの種類を選択します (**アクション**または**応答**)。|  
|**[Attachments]**|クリックして**追加**、添付ファイルを含むフォルダーに移動し、クリックして**オープン**します。|  
|**メッセージを送信します。**|クリックしてメッセージを送信します。|  
|**ステータス**|このフィールドでは、アクションの状態を確認します。|  
  
## <a name="remarks"></a>コメント  
 LOBApplication ユーティリティは、指定されたプロパティに基づいてメッセージを作成し、それを取引先に送信します。 このユーティリティは、メッセージの Service Content データを BTARNDATA データベースの MessageFromLOB テーブルに書き込み、 アクション メッセージの送信をシミュレートします。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK の LOBApplication フォルダー内の SampleInstances フォルダーに含まれているサンプル メッセージは、ホーム組織の場合は 123456789、取引先組織の場合は 987654321 という、グローバル ビジネス識別子 (GBI) を持つようにあらかじめ設定されています。 これ以外の GBI を使用するには、サンプル メッセージをテキスト エディターで変更する必要があります。  
  
 LOBApplication ユーティリティは、メッセージを送信する基幹業務 (LOB) デスクトップ プログラムをシミュレートするために使用します。 LOBWebApplication ユーティリティは、メッセージを送信する基幹業務 (LOB) Web アプリケーションをシミュレートするために使用します。  
  
## <a name="see-also"></a>参照  
 [ユーティリティ](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)   
 [LOBWebApplication](../../adapters-and-accelerators/accelerator-rosettanet/lobwebapplication.md)
